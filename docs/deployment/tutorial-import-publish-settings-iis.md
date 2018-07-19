---
title: 게시 게시 설정을 가져와서 IIS
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to IIS
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6df935578955d3c72b6f4fa61efdf614229bca0
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38808467"
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>IIS에 응용 프로그램을 가져와서 게시할 Visual Studio에서 게시 설정

사용할 수는 **게시** 가져오는 도구를 게시 설정 및 앱을 배포 합니다. 이 문서에서는 사용 하 여 IIS에 대 한 설정을 사용할 수 있지만 가져오려는 비슷한 단계에 대 한 설정을 게시 [Azure App Service](../deployment/tutorial-import-publish-settings-azure.md)합니다. 일부 시나리오에서는 게시 설정 프로필을 Visual Studio의 각 설치에 대 한 IIS에 배포를 수동으로 구성 하는 보다 빠르게 수 사용 합니다.

이러한 단계는 Visual Studio에서 ASP.NET, ASP.NET Core 및.NET Core 앱에 적용 됩니다. 단계는 Visual Studio 2017 버전 15.6에 해당 합니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 게시 설정 파일을 생성할 수 있도록 IIS 구성
> * 게시 설정 파일 만들기
> * Visual Studio로 게시 설정 파일 가져오기
> * IIS에 앱 배포

게시 설정 파일 (*\*.publishsettings*) 게시 프로필 다릅니다 (*\*.pubxml*) Visual Studio에서 생성 합니다. 게시 설정 파일을 IIS 또는 Azure App Service 또는 것 수동으로 만들 수 있습니다, 만들어지고 Visual Studio로 가져올 수 있습니다.

> [!NOTE]
> Visual Studio 게시 프로필을 복사 해야 하는 경우 (\*.pubxml 파일) 다른 Visual Studio의 한 설치에서 게시 프로필을 찾을 수 있습니다  *\<profilename\>.pubxml*, 에  *\\< projectname\>\Properties\PublishProfiles* 관리 되는 프로젝트 형식에 대 한 폴더입니다. 웹 사이트의 경우 아래에서 확인 합니다 *\App_Data* 폴더입니다. 게시 프로필은 MSBuild XML 파일입니다.

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017이 설치 되어 있어야 하며 **ASP.NET** 하 고 **.NET Framework** 개발 워크 로드. .NET Core 앱에 대 한 작업도 수행 해야 합니다 **.NET Core** 워크 로드.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

* IIS에서 게시 설정 파일을 생성 하려면 Windows Server 2012 또는 Windows Server 2016을 실행 하는 컴퓨터 있어야 하며 올바르게 구성 된 IIS 웹 서버 역할이 있어야 합니다. ASP.NET 4.5 또는 ASP.NET Core 설치 되어야 합니다. ASP.NET Core에 대 한 참조 [IIS에 게시](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)합니다. ASP.NET 4.5에 대 한 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Visual Studio에서 새 ASP.NET 프로젝트 만들기

1. Visual Studio를 실행 하는 컴퓨터를 선택 **파일** > **새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**를 선택한 다음 가운데 창에서 하나 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 또는 (C#만 해당) **ASP.NET Core 웹 응용 프로그램**를 클릭 하 고 **확인**합니다.

    지정 된 프로젝트 템플릿이 보이지 않으면 클릭 합니다 **Visual Studio 설치 관리자 열기** 의 왼쪽된 창에서 링크는 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 필요한 Visual Studio 워크 로드를 설치 해야 하는 데이 문서의 필수 구성 요소를 참조 하세요.

1. 선택할 **MVC** (.NET Framework) 또는 **웹 응용 프로그램 (모델-뷰-컨트롤러)** (.NET Core)에 대 한 했는지 **인증 안 함** 를 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 누릅니다 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택할 **빌드할** > **솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="install-and-configure-web-deploy-on-windows-server"></a>설치 및 Windows Server에서 웹 배포를 구성 합니다.

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows server IIS에서 게시 설정 파일 만들기

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio에서 게시 설정 가져오기 및 배포

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

앱을 성공적으로 배포 하는 자동으로 시작 해야 합니다. Visual Studio에서 시작 되지 않으면, IIS에서 앱을 시작 합니다. ASP.NET Core에 대 한 응용 프로그램 풀에 대 한 필드는 확인 해야 합니다 **DefaultAppPool** 로 설정 된 **관리 코드 없음**합니다.

## <a name="next-steps"></a>다음 단계

게시 설정 파일을 생성 합니다.이 자습서에서는 Visual Studio로 가져온 및 IIS에 ASP.NET 앱을 배포 합니다. Visual Studio의 다른 게시 옵션의 개요를 확인할 수 있습니다.

> [!div class="nextstepaction"]
> [배포 소개](../deployment/deploying-applications-services-and-components.md)
