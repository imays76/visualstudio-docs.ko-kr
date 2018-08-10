---
title: 가져와서 Azure에 게시 게시 설정
ms.description: Create and import a publishing profile to deploy an application from Visual Studio to Azure App Service
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
ms.openlocfilehash: 2b4b0e4ea963f20199267f32a8c87440c8cc350b
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38808323"
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>가져와서 Azure App Service에 응용 프로그램을 게시 합니다. Visual Studio에서 게시 설정

사용할 수는 **게시** 가져오는 도구를 게시 설정 및 앱을 배포 합니다. 이 문서에서는 사용 하 여 Azure App Service에 대 한 설정을 사용할 수 있지만 가져오려는 비슷한 단계에서 게시 설정을 [IIS](../deployment/tutorial-import-publish-settings-iis.md)합니다. 일부 시나리오에서는 게시 설정 프로필을 수동으로 Visual Studio의 각 설치에 대 한 서비스에 배포를 구성 하는 보다 빠르게 수 사용 합니다.

이러한 단계는 Visual Studio에서 ASP.NET, ASP.NET Core 및.NET Core 앱에 적용 됩니다. 가져올 수도 있습니다에 대 한 설정을 [Python](../python/publishing-python-web-applications-to-azure-from-visual-studio.md) 앱. 단계는 Visual Studio 2017 버전 15.6에 해당 합니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * Azure App Service에서 게시 설정 파일을 생성 합니다.
> * Visual Studio로 게시 설정 파일 가져오기
> * Azure App Service에 앱 배포

게시 설정 파일 (*\*.publishsettings*) 게시 프로필 다릅니다 (*\*.pubxml*) Visual Studio에서 생성 합니다. 게시 설정 파일을 Azure App Service에서 만들어지고 Visual Studio로 가져올 수 있습니다.

> [!NOTE]
> Visual Studio 게시 프로필을 복사 해야 하는 경우 (*\*.pubxml* 파일) 다른 Visual Studio의 한 설치에서 게시 프로필을 찾을 수 있습니다  *\<profilename\>.pubxml*를  *\\< projectname\>\Properties\PublishProfiles* 관리 되는 프로젝트 형식에 대 한 폴더입니다. 웹 사이트의 경우 아래에서 확인 합니다 *\App_Data* 폴더입니다. 게시 프로필은 MSBuild XML 파일입니다.

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017이 설치 되어 있어야 하며 **ASP.NET** 및. **NET Framework** 개발 워크 로드. .NET Core 앱에 대 한 작업도 수행 해야 합니다. **.NET Core** 워크 로드.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

* Azure App Service를 만듭니다. 자세한 지침은 [Visual Studio를 사용 하 여 Azure에 ASP.NET Core 웹 앱 배포](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)합니다.

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Visual Studio에서 새 ASP.NET 프로젝트 만들기

1. Visual Studio를 실행 하는 컴퓨터를 선택 **파일** > **새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**를 선택한 다음 가운데 창에서 하나 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 또는 (C#만 해당) **ASP.NET Core 웹 응용 프로그램**를 클릭 하 고 **확인**합니다.

    지정 된 프로젝트 템플릿이 보이지 않으면 클릭 합니다 **Visual Studio 설치 관리자 열기** 의 왼쪽된 창에서 링크는 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 필요한 Visual Studio 워크 로드를 설치 해야 하는 데이 문서의 필수 구성 요소를 참조 하세요.

1. 선택할 **MVC** (.NET Framework) 또는 **웹 응용 프로그램 (모델-뷰-컨트롤러)** (.NET Core)에 대 한 했는지 **인증 안 함** 를 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 누릅니다 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택할 **빌드할** > **솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>Azure App Service에서 게시 설정 파일 만들기

1. Azure portal에서 Azure App Service를 엽니다.

1. 클릭 **게시 프로필 가져오기** 프로 파일을 로컬로 저장 합니다.

    ![게시 프로필 가져오기](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    사용 하 여 파일을 *.publishsettings* 파일 확장명을는 저장 위치에서 생성 되었습니다. 다음 코드를 보다 읽기 쉬운 형식) (파일의 일부 예제를 보여 줍니다.

    ```xml
    <publishData>
      <publishProfile
        profileName="DeployASPDotNetCore - Web Deploy"
        publishMethod="MSDeploy"
        publishUrl="deployaspdotnetcore.scm.azurewebsites.net:443"
        msdeploySite="DeployASPDotNetCore"
        userName="$DeployASPDotNetCore"
        userPWD="abcdefghijklmnopqrstuzwxyz"
        destinationAppUrl="http://deployaspdotnetcore20180508031824.azurewebsites.net"
        SQLServerDBConnectionString=""
        mySQLDBConnectionString=""
        hostingProviderForumLink=""
        controlPanelLink="http://windows.azure.com"
        webSystem="WebSites">
        <databases />
      </publishProfile>
    </publishData>
    ```
    일반적으로 이전 *.publishsettings 파일을 웹 배포 하 고 하나를 사용 하 여 FTP를 사용 하 여 배포를 배포 하려면 Visual Studio에서 사용할 수 있는 두 개의 게시 프로필을 포함 합니다. 위의 코드는 웹 배포 프로필을 보여 줍니다. 프로필을 가져올 때 두 프로필이 모두 나중에 가져올 수 됩니다.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio에서 게시 설정 가져오기 및 배포

[!INCLUDE [import publish settings](../deployment/includes/import-publish-settings-vs.md)]

## <a name="next-steps"></a>다음 단계

게시 설정 파일을 생성 합니다.이 자습서에서는 Visual Studio로 가져온 및 Azure App Service에 ASP.NET 앱을 배포 합니다. Visual Studio에서 게시 옵션의 개요를 확인할 수 있습니다.

> [!div class="nextstepaction"]
> [배포 소개](../deployment/deploying-applications-services-and-components.md)
