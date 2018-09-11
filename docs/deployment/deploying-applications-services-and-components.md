---
title: 배포 기능 둘러보기
description: Visual Studio에서 앱을 배포 하기 위한 옵션에 알아봅니다.
ms.custom: mvc
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- .NET applications, deploying
- components [Visual Studio], deploying
- installers
- publishing
- deploying applications [Visual Studio]
- deploying applications [Visual Studio], about deploying applications
- components [.NET Framework], deploying
ms.assetid: 63fcdd5b-2e54-4210-9038-65bc23167725
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83b6449d3f9fb41280d9e0b051c5baf3edbf5a66
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44320555"
---
# <a name="quickstart-first-look-at-deployment-in-visual-studio"></a>빠른 시작: Visual Studio에서 배포 소개

응용 프로그램, 서비스 또는 구성 요소를 배포 하 여 배포할 있습니다 클라우드 또는 다른 컴퓨터, 장치 또는 서버에 설치 합니다. Visual Studio에서 필요한 배포 유형에 적합한 방법을 선택할 수 있습니다. (여러 앱 유형을 여기 설명 되지 않은 명령줄 배포 또는 NuGet와 같은 다른 배포 도구를 지원 합니다.)

빠른 시작 및 단계별 배포 지침은 자습서를 참조 하세요. 배포 옵션의 개요를 보려면 [내게 적합 한 게시 옵션은?](deploying-applications-services-and-components-resources.md#what-publishing-options-are-right-for-me)합니다.

## <a name="deploy-to-local-folder"></a>로컬 폴더에 배포

테스트, 또는 다른 도구 최종 배포에 사용 되는 스테이징 된 배포를 시작 하려면 일반적으로 로컬 폴더에 배포가 됩니다.

- **ASP.NET**, **ASP.NET Core**합니다 **Node.js**를 **Python**, 및. **.NET Core**: 게시 도구를 사용 하 여 로컬 폴더에 배포 되도록 합니다. 사용 가능한 정확한 옵션 앱 형식에 따라 달라 집니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시**합니다. (모든 게시 프로필을 이전에 구성한 경우 다음 눌러야 **새 프로필 만들기**.) 그런 다음 선택 **폴더**합니다. 자세한 내용은 [로컬 폴더에 배포](quickstart-deploy-to-local-folder.md)합니다.

    ![선택 게시](../deployment/media/quickstart-publish.png)

- **Visual c + + 런타임**: 로컬 배포 또는 정적 연결을 사용 하 여 Visual c + + 런타임을 배포할 수 있습니다. 자세한 내용은 [네이티브 데스크톱 응용 프로그램 배포 (Visual c + +)](/cpp/ide/deploying-native-desktop-applications-visual-cpp)합니다.

## <a name="publish-to-azure"></a>Azure에 게시

- **ASP.NET**, **ASP.NET Core**를 **Python**, 및 **Node.js**: 게시 도구를 사용 하 여 Azure App Service 또는 Azure Virtual 신속 하 게 앱을 배포 하려면 컴퓨터입니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다. (모든 게시 프로필을 이전에 구성한 경우 다음 눌러야 **새 프로필 만들기**.) 게시 대화 상자에서 하나를 선택할 **App Service** 하거나 **Azure Virtual Machines**, 구성 단계를 따릅니다.

    ![Azure App Service를 선택](../deployment/media/quickstart-publish-azure.png "Azure App Service를 선택 합니다.")

    Visual Studio 2017 버전 15.7 이상에서 ASP.NET Core 앱을 배포할 수 있습니다 **Linux 용 App Service**합니다.

    Python 앱에 대 한 참조도 [Python-Azure App Service에 게시](/visualstudio/python/publishing-python-web-applications-to-azure-from-visual-studio?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)합니다.

    간략 한 소개를 참조 하세요 [Azure에 게시](quickstart-deploy-to-azure.md) 하 고 [Linux에 게시](quickstart-deploy-to-linux.md)합니다. 도 참조 하세요 [ASP.NET Core 앱을 Azure에 게시](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)합니다. Git를 사용 하 여 배포를 참조 하세요 [Git 사용 하 여 Azure에 ASP.NET Core 연속 배포](/aspnet/core/publishing/azure-continuous-deployment)합니다.

    Visual Studio로 Azure App Service에서 게시 프로필 가져오기에 대 한 자세한 내용은 [게시 설정을 가져와서 Azure에 배포](../deployment/tutorial-import-publish-settings-azure.md)합니다.

    > [!NOTE]
    > Azure 계정이 아직 없는 경우 [여기서 등록](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)합니다.

## <a name="publish-to-web-or-deploy-to-network-share"></a>웹에 게시 또는 네트워크 공유에 배포

- **ASP.NET**, **ASP.NET Core**합니다 **Node.js**, 및 **Python**: 게시 도구를 사용 하 여 FTP 나 Web Deploy를 사용 하 여 웹 사이트에 배포할 수 있습니다. 자세한 내용은 [웹 사이트로 배포](quickstart-deploy-to-a-web-site.md)합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다. (모든 게시 프로필을 이전에 구성한 경우 다음 눌러야 **새 프로필 만들기**.) 게시 도구에서 구성 단계에 따라 원하는 옵션을 선택 합니다.

    ![IIS, FTP 등을 선택 합니다.](../deployment/media/quickstart-publish-iis-ftp.png)

    Visual Studio에서 게시 프로필 가져오기에 대 한 자세한 내용은 [게시 설정 가져오기 및 IIS에 배포](../deployment/tutorial-import-publish-settings-iis.md)합니다.

    ASP.NET 응용 프로그램 및 서비스는 여러 가지 다른 방법으로에서 배포할 수 있습니다. 자세한 내용은 [배포 ASP.NET 웹 응용 프로그램 및 서비스](http://www.asp.net/aspnet/overview/deployment)합니다.

- **Visual c + + 런타임**: 중앙 배포를 사용 하 여 Visual c + + 런타임을 배포할 수 있습니다. 자세한 내용은 [네이티브 데스크톱 응용 프로그램 배포 (Visual c + +)](/cpp/ide/deploying-native-desktop-applications-visual-cpp)합니다.

- **Windows 데스크톱** 웹 서버 또는 ClickOnce 배포를 사용 하 여 네트워크 파일 공유에는 Windows 데스크톱 응용 프로그램을 게시할 수 있습니다. 이렇게 하면 사용자가 클릭 한 번으로 응용 프로그램을 설치할 수 있습니다. 자세한 내용은 [ClickOnce를 사용 하 여 데스크톱 앱 배포](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) 하 고 [ClickOnce를 사용 하 여 네이티브 앱을 배포](/cpp/ide/clickonce-deployment-for-visual-cpp-applications)합니다.

## <a name="publish-to-microsoft-store"></a>Microsoft Store 게시

Visual Studio에서 Microsoft Store 배포에 대 한 앱 패키지를 만들 수 있습니다.

- **UWP**: 앱을 패키지 하 고 메뉴 항목을 사용 하 여 배포할 수 있습니다. 자세한 내용은 [Visual Studio를 사용 하 여 UWP 앱 패키지](/windows/uwp/packaging/packaging-uwp-apps)합니다.

    ![응용 프로그램 패키지 만들기](../deployment/media/feature-tour-create-app-package.jpg)

- **Windows 데스크톱**: Visual Studio 2017 버전 15.4부터 데스크톱 브리지를 사용 하 여 Microsoft Store 배포할 수 있습니다. 이 위해 Windows 응용 프로그램 패키징 프로젝트를 만들어 시작 합니다. 자세한 내용은 [Microsoft Store (데스크톱 브리지) 용 데스크톱 앱 패키지](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)합니다.

    ![데스크톱 브리지](../deployment/media/feature-tour-desktop-bridge.png)

## <a name="deploy-to-a-device-uwp"></a>(UWP) 장치에 배포

장치에서 테스트를 위해 UWP 앱을 배포 하는 경우 참조 [원격 컴퓨터에서 Visual Studio에서 UWP 앱 실행](../debugger/run-windows-store-apps-on-a-remote-machine.md)합니다.

## <a name="create-an-installer-package-windows-client"></a>설치 관리자 패키지 (Windows 클라이언트) 만들기

필요한 경우 더 보다 데스크톱 응용 프로그램의 복잡 한 설치 [ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) 에 제공 된 설치 관리자 패키지, 설치 프로젝트 또는 사용자 지정 부트스트래퍼를 만들 수 있습니다.

- 사용 하 여 WiX MSI 기반 설치 관리자를 만들 수 있습니다 합니다 [WiX 도구 집합 Visual Studio 2017 확장](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)합니다.

- [InstallShield](https://www.flexerasoftware.com/producer/products/software-installation/installshield-software-installer/tab/requirements) Flexera Software의 Visual Studio 2017 (Community Edition을 지원 되지 않습니다.)를 사용 하 여 사용할 수 있습니다. InstallShield Limited Edition은 더 이상 포함 된 Visual Studio 및 Visual Studio 2017에서 지원 되지 않습니다. 확인 [Flexera Software](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) 추후 가용성에 대 한 합니다.

- 설치 프로젝트 (vdproj)를 만들려는 경우 설치 합니다 [Visual Studio 2017 설치 관리자 프로젝트 확장](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.MicrosoftVisualStudio2017InstallerProjects#overview)합니다.

- 부트스트래퍼 이라고 일반 설치 관리자를 구성 하 여 데스크톱 응용 프로그램에 대 한 필수 구성 요소를 설치할 수 있습니다. 자세한 내용은 [응용 프로그램 배포 필수 구성 요소](../deployment/application-deployment-prerequisites.md)합니다.

## <a name="deploy-to-test-lab"></a>테스트 환경에 배포

더욱 정교한 개발과 가상 환경에 응용 프로그램을 배포 하 여 테스트를 사용할 수 있습니다. 자세한 내용은 [테스트 랩 환경에서](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md)합니다.

## <a name="devops-deployment"></a>DevOps 배포

팀 환경에서 앱의 연속 배포를 사용 하도록 설정 하려면 Azure 파이프라인을 사용할 수 있습니다. 자세한 내용은 [Azure 파이프라인](/azure/devops/pipelines/index?view=vsts) 하 고 [Azure에 배포](/azure/devops/deploy-azure/index?view=vsts)합니다.

## <a name="deployment-for-other-app-types"></a>다른 유형의 앱에 대 한 배포

| 앱 형식 | 배포 시나리오 | 링크 |
| --- | --- | --- |
| **Office 앱** | Visual Studio에서 Office 용 추가 기능을 게시할 수 있습니다. | [Office 추가 기능을 게시 및 배포](https://dev.office.com/docs/add-ins/publish/publish) |
| **WCF 또는 OData 서비스**  | 다른 응용 프로그램 웹 서버에 배포한 WCF RIA 서비스를 사용할 수 있습니다. | [WCF Data Services 개발 및 배포](/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **LightSwitch** | LightSwitch Visual Studio 2017에서 더 이상 지원 되지 않지만 Visual Studio 2015에서 및 이전 버전 배포할 수 없습니다. | [LightSwitch 응용 프로그램 배포](https://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) |

## <a name="next-steps"></a>다음 단계

이 자습서에서는 서로 다른 응용 프로그램에 대 한 배포 옵션 둘러보기를 걸렸습니다.

> [!div class="nextstepaction"]
> [게시 옵션에 대해 내게 적합 한?](deploying-applications-services-and-components-resources.md#what-publishing-options-are-right-for-me)
