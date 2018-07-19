---
title: 웹 배포를 사용 하 여 IIS에 ASP.NET 배포
ms.custom: ''
ms.date: 06/04/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 4705ca6e72001f8930e2fa4270515df53e1213a8
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080852"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>ASP.NET 웹 배포를 사용 하 여 Visual Studio에서 원격 IIS 컴퓨터에 배포

이 문서에서는 설정 Visual Studio 2017 ASP.NET MVC 4.5.2 응용 프로그램을 구성 하 고 IIS에 배포 하는 방법을 설명 합니다. 이 문서에는 Windows 서버에 iis 기본 구성 설정 및 Visual Studio에서 앱을 배포 하는 단계가 포함 됩니다. 이러한 단계는 서버에 필요한 구성 요소를 설치 하 고을 배포할 준비가 포함 됩니다. ASP.NET Core 응용 프로그램을 배포 하는 경우 몇 가지 단계가 서로 다릅니다. ASP.NET Core 앱을 배포 하려면 참조 [게시 설정을 가져와서 IIS에 응용 프로그램 게시](../deployment/tutorial-import-publish-settings-iis.md) 지침에 대 한 합니다. 일부 ASP.NET 및 ASP.NET Core 시나리오에서는 하기가 더 빠르게 배포 게시 설정을 가져와서 IIS입니다.

이러한 절차 이러한 서버 구성에서 테스트 되었습니다.
* Windows Server 2012 R2 및 IIS 8 (Windows Server 2008 R2 용 server 단계가 다릅니다)

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>ASP.NET 4.5.2를 만들려면 Visual Studio 컴퓨터에서 응용 프로그램
  
1. Visual Studio를 실행 하는 컴퓨터를 선택 **파일** > **새 프로젝트**합니다.

1. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **웹**를 선택한 다음 가운데 창에서 하나 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 을 클릭 한 다음 **확인**합니다.

    지정 된 프로젝트 템플릿이 보이지 않으면 클릭 합니다 **Visual Studio 설치 관리자 열기** 의 왼쪽된 창에서 링크는 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 필요한 Visual Studio 워크 로드를 설치 해야 하는 데이 문서의 필수 구성 요소를 참조 하세요.

1. 선택할 **MVC** (.NET Framework) 했는지 **인증 안 함** 를 선택한 다음 클릭 **확인**합니다.

1. 같은 이름을 입력 **MyWebApp** 누릅니다 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

1. 선택할 **빌드할** > **솔루션 빌드** 프로젝트를 빌드합니다.

## <a name="install-and-configure-iis-on-windows-server"></a>설치 하 고 Windows Server에서 IIS를 구성 합니다.

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server에서 브라우저 보안 설정 업데이트

보안 강화 구성 (기본적으로 사용 됩니다) Internet Explorer에서 사용 하는 경우 일부 웹 서버 구성 요소를 다운로드할 수 있도록 신뢰할 수 있는 사이트로 일부 도메인을 추가 해야 있습니다. 으로 이동 하 여 신뢰할 수 있는 사이트 추가 **인터넷 옵션** > **Security** > **신뢰할 수 있는 사이트** > **사이트** . 다음 도메인을 추가 합니다.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- iis.net

소프트웨어를 다운로드 하면 다양 한 웹 사이트 스크립트 및 리소스를 로드 하는 권한 부여에 대 한 요청 표시 될 수 있습니다. 이러한 리소스 중 일부는 필요 하지 않지만 프로세스를 간소화 하기 위해 클릭 **추가** 메시지가 표시 되 면 합니다.

## <a name="install-aspnet-45-on-windows-server"></a>Windows Server에 ASP.NET 4.5를 설치 합니다.

IIS에서 ASP.NET을 설치 하려면 자세한 정보를 보려는 경우 참조 하세요 [ASP.NET 3.5 및 ASP.NET 4.5를 사용 하 여 IIS 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

1. 서버 관리자의 왼쪽된 창에서 선택 **IIS**합니다. 서버를 마우스 오른쪽 단추로 누르고 **인터넷 정보 서비스 (IIS) 관리자**합니다.

1. 웹 플랫폼 설치 관리자 (WebPI)를 사용 하 여 ASP.NET 4.5를 설치 (Windows Server 2012 R2의 서버 노드를 선택할 **새 웹 플랫폼 구성 요소 가져오기** 및 ASP.NET에 대 한 다음 검색)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Windows Server 2008 R2를 사용 하는 경우이 명령을 사용 하는 ASP.NET 4를 설치 합니다.

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. 시스템 다시 시작 (하거나 실행할 **net stop was /y** 뒤 **net start w3svc** 시스템 경로에 대 한 변경 내용을 선택 하려면 명령 프롬프트에서).

## <a name="install-web-deploy-36-on-windows-server"></a>설치 웹 배포 3.6에 Windows Server

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="configure-aspnet-web-site-on-the-windows-server-computer"></a>Windows Server 컴퓨터에서 ASP.NET 웹 사이트 구성

1. Windows 탐색기를 열고 새 폴더를 만듭니다 **C:\Publish**ASP.NET 프로젝트를 나중에 배포할가 있습니다.

2. 열려 있지 않으면 엽니다는 **인터넷 정보 서비스 (IIS) 관리자**합니다. (서버 관리자의 왼쪽된 창에서 선택 **IIS**합니다. 서버를 마우스 오른쪽 단추로 누르고 **인터넷 정보 서비스 (IIS) 관리자**.)

3. 아래 **연결** 왼쪽된 창에서로 이동 **사이트**합니다.

4. 선택 합니다 **기본 웹 사이트**, 선택 **기본 설정**, 설정 및는 **실제 경로** 에 **C:\Publish**합니다.

5. **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가**를 선택합니다.

6. 설정 합니다 **별칭** 필드를 **MyASPApp**, 응용 프로그램 풀 기본값 (**DefaultAppPool**), 설정 및 합니다 **실제 경로** 를 **C:\Publish**합니다.

7. 아래 **연결**를 선택 **응용 프로그램 풀**합니다. 오픈 **DefaultAppPool** 응용 프로그램 풀 필드를 설정 하 고 **ASP.NET v4.0** (ASP.NET 4.5는 응용 프로그램 풀에 대 한 옵션이 아님).

8. IIS 관리자에서 선택한 사이트를 선택할 **사용 권한 편집**, 해당 IUSR, IIS_IUSRS, 또는 사용자 응용 프로그램 풀은 읽기 및 실행 권한이 있는 권한 있는 사용자에 대해 구성 되었는지 확인 합니다. 이러한 사용자에이 게가 하나도 없으면 IUSR 읽기 및 실행 권한이 있는 사용자로 추가 합니다.

## <a name="publish-and-deploy-the-app-using-web-deploy-from-visual-studio"></a>게시 하 고 Visual Studio에서 웹 배포를 사용 하 여 앱 배포

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

또한 포트 문제를 해결 하는 방법은 다음 섹션을 참조 해야 합니다.

## <a name="troubleshoot-open-required-ports-on-windows-server"></a>Windows Server에서 필요한 포트를 열고 문제 해결:

대부분의 설치 프로그램에서 ASP.NET 및 웹 배포 설치를 통해 필요한 포트가 열려 있습니다. 그러나 포트가 열려 있는지 확인 해야 합니다.

> [!NOTE]
> Azure VM에서 포트를 통해 열어야 합니다 [네트워크 보안 그룹](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80)합니다. 

필요한 포트:

* 80-IIS에 대 한 필요합니다.
* 8172-Visual Studio에서 앱을 배포 하려면 웹 배포에 대 한 필요 합니다.

1. Windows Server에서 포트를 열려면 합니다 **시작** 메뉴에서 검색 **Windows Firewall with Advanced Security**합니다.

2. 선택한 **인바운드 규칙** > **새 규칙** > **포트**합니다. 선택 **다음** 아래에서 **특정 로컬 포트**포트 번호를 입력, 클릭 **다음**, 다음 **연결을 허용**, 다음을 클릭 하 고 이름을 추가 합니다 (**IIS**를 **Web Deploy**, 또는 **msvsmon**) 인바운드 규칙에 대 한 합니다.

    Windows 방화벽 구성에 대 한 자세한 내용은 참조 하세요 [원격 디버깅용 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)합니다.

3. 기타 필요한 포트에 대 한 추가 규칙을 만듭니다.

## <a name="next-steps"></a>다음 단계

게시 설정 파일을 생성 합니다.이 자습서에서는 Visual Studio로 가져온 및 IIS에 ASP.NET 앱을 배포 합니다. 가져와서 배포할 수도 있습니다 게시 설정 합니다.

> [!div class="nextstepaction"]
> [배포 게시 설정을 가져와서 IIS](../deployment/tutorial-import-publish-settings-iis.md)
