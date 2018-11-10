---
title: Azure 클라우드 서비스 또는 가상 컴퓨터에서 Visual Studio 디버깅 | Microsoft Docs
description: Visual Studio에서 클라우드 서비스 또는 가상 컴퓨터 디버그
author: mikejo5000
manager: douge
ms.assetid: 945e06e0-2100-41af-b218-72347367ddab
ms.topic: conceptual
ms.custom: vs-azure
ms.workload: azure-vs
ms.date: 11/11/2016
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.openlocfilehash: b2c67ce81a42df4a17761fcee2dcd2f8a67c4941
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002943"
---
# <a name="debugging-an-azure-cloud-service-or-virtual-machine-in-visual-studio"></a>Azure 클라우드 서비스 또는 가상 컴퓨터에서 Visual Studio 디버깅

Visual Studio Azure cloud services 및 virtual machines를 디버깅 하는 것에 대 한 다른 옵션이 있습니다.

## <a name="debug-your-cloud-service-on-your-local-computer"></a>로컬 컴퓨터에서 클라우드 서비스 디버그

시간을 절약할 수 및 Azure를 사용 하 여 비용 계산 에뮬레이터는 로컬 컴퓨터에서 클라우드 서비스를 디버그 합니다. 배포 하기 전에 로컬로 서비스를 디버깅, 계산 시간에 대 한 비용을 지불 하지 않고 안정성과 성능을 향상 시킬 수 있습니다. 그러나 일부 오류를 실행할 때만 클라우드 서비스를 Azure에서 발생할 수 자체입니다. 서비스를 게시 하 고 역할 인스턴스에 디버거를 연결 하는 경우 원격 디버깅을 사용 하는 경우 이러한 오류를 디버그할 수 있습니다.

에뮬레이터는 Azure Compute 서비스를 시뮬레이션 하 고 테스트 하 고 배포 하기 전에 클라우드 서비스를 디버그할 수 있도록 로컬 환경에서 실행 됩니다. 에뮬레이터는 역할 인스턴스의 수명 주기를 처리 하 고 로컬 저장소 같은 시뮬레이트된 리소스에 대 한 액세스를 제공 합니다. 를 디버그 하거나 Visual Studio에서 서비스를 실행 하는 경우 자동으로 백그라운드 응용 프로그램으로 에뮬레이터를 시작 하 고 에뮬레이터에 서비스를 배포 합니다. 로컬 환경에서 실행 될 때 서비스를 보려면 에뮬레이터를 사용할 수 있습니다. 정식 버전 또는 에뮬레이터의 express 버전을 실행할 수 있습니다. (Azure 2.3부터 에뮬레이터의 express 버전은 기본값입니다.) 참조 [Emulator Express를 사용 하 여 실행 하 고 클라우드 서비스를 로컬로 디버깅할](vs-azure-tools-emulator-express-debug-run.md)합니다.

### <a name="to-debug-your-cloud-service-on-your-local-computer"></a>로컬 컴퓨터에서 클라우드 서비스를 디버깅 하려면

1. 메뉴 모음에서 **디버그**하십시오 **디버깅 시작** Azure 클라우드 서비스 프로젝트를 실행 합니다. 대신, f5 키를 눌러 수 있습니다. 계산 에뮬레이터를 시작 하는 메시지가 표시 됩니다. 에뮬레이터를 시작할 때 시스템 트레이 아이콘을 확인 합니다.

    ![시스템 트레이의 azure 에뮬레이터](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC783828.png)

2. 계산 에뮬레이터의 알림 영역에서 Azure 아이콘에 대 한 바로 가기 메뉴를 열어 사용자 인터페이스를 표시 하 고 선택한 **Compute 에뮬레이터 UI 표시**합니다.

    UI의 왼쪽된 창에서는 현재 계산 에뮬레이터 및 각 서비스가 실행 되는 역할 인스턴스가 배포 되어 있는 서비스를 보여 줍니다. 서비스 또는 오른쪽 창에서 수명 주기, 로깅 및 진단 정보를 표시 하는 역할을 선택할 수 있습니다. 포함 된 창의 위쪽 여백에 포커스를 배치 하면 오른쪽 창에 맞게 확장 됩니다.

3. 명령을 선택 하 여 응용 프로그램을 통해 단계를 **디버그** 메뉴 및 코드에 중단점을 설정 합니다. 디버거에서 응용 프로그램을 단계별로 창 응용 프로그램의 현재 상태로 업데이트 됩니다. 디버깅을 중지 하면 응용 프로그램 배포가 삭제 됩니다. 응용 프로그램에 웹 역할이 포함 하 고 웹 브라우저를 시작 하도록 시작 동작 속성을 사용 하도록 설정한 경우 Visual Studio는 브라우저에서 웹 응용 프로그램을 시작 합니다. 서비스 구성에서 역할의 인스턴스 수를 변경 하는 경우에 클라우드 서비스를 중지 하 고 역할의 이러한 새 인스턴스를 디버깅할 수 있도록 디버깅을 다시 시작 해야 합니다.

    **참고:** 실행 또는 디버깅 서비스를 중지 하면 로컬 계산 에뮬레이터 및 저장소 에뮬레이터가 중지 되지 않습니다. 알림 영역에서 해당 작업을 명시적으로 중지 해야 합니다.

## <a name="debug-a-cloud-service-in-azure"></a>Azure에서 클라우드 서비스 디버그

원격 컴퓨터에서 클라우드 서비스를 디버깅 하려면 활성화 해야 해당 기능은 명시적으로 필요한 서비스 (예: msvsmon.exe) 역할 인스턴스가 실행 되는 가상 컴퓨터에 설치 됩니다 있도록 클라우드 서비스를 배포 하는 경우. 서비스를 게시할 때 원격 디버깅을 사용 하지 않은 경우 원격 디버깅을 사용한 서비스를 다시 게시 해야 합니다.

클라우드 서비스에 대 한 원격 디버깅을 사용 하는 경우 성능이 저하 또는 추가 요금이 발생 하지 않습니다. 사용 하지 마십시오 프로덕션 서비스에서 원격 디버깅 서비스를 사용 하는 클라이언트 부정적인 영향을 받을 수 있으므로.

> [!NOTE]
> Visual Studio에서 클라우드 서비스를 게시할 때 설정할 수 있습니다 **IntelliTrace** 해당 서비스의.NET Framework 4 또는.NET Framework 4.5를 대상으로 하는 모든 역할에 대 한 합니다. 사용 하 여 **IntelliTrace**, 과거에 역할 인스턴스에서 발생 한 이벤트를 검토 하 고 해당 시점부터 컨텍스트를 재현할 수 있습니다. 참조 [IntelliTrace 및 Visual Studio를 사용 하 여 게시 된 클라우드 서비스 디버깅](http://go.microsoft.com/fwlink/?LinkID=623016) 하 고 [IntelliTrace를 사용 하 여](https://msdn.microsoft.com/library/dd264915.aspx)입니다.

### <a name="to-enable-remote-debugging-for-a-cloud-service"></a>클라우드 서비스에 대 한 원격 디버깅을 사용 하도록 설정 하려면

1. Azure 프로젝트에 대 한 바로 가기 메뉴를 열고 선택한 **게시**합니다.

2. 선택 된 **스테이징** 환경 및 **디버그** 구성 합니다.

    이것이 단지 지침일 뿐입니다. 테스트 환경의 프로덕션 환경에서 실행 하도록 선택할 수 있습니다. 그러나 있습니다 부정적인 영향을 줄 수 사용자가 프로덕션 환경에서 원격 디버깅을 사용 하는 경우. 릴리스 구성을 선택할 수 있지만 디버그 구성을 쉽게 디버깅할 수 있습니다.

    ![디버그 구성 선택](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746717.gif)

3. 일반 단계를 수행 하지만 선택 합니다 **모든 역할에 대해 원격 디버거 사용** 확인란 합니다 **고급 설정** 탭 합니다.

    ![디버그 구성](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746718.gif)

### <a name="to-attach-the-debugger-to-a-cloud-service-in-azure"></a>Azure에서 클라우드 서비스에 디버거를 연결 하려면

1. 서버 탐색기에서 클라우드 서비스에 대 한 노드를 확장 합니다.

2. 연결을 선택한 다음 선택 하려는 역할 또는 역할 인스턴스에 대 한 바로 가기 메뉴를 열고 **디버거 연결**합니다.

    역할을 디버깅 하는 경우 Visual Studio 디버거는 해당 역할의 각 인스턴스에 연결 합니다. 디버거는 코드 줄을 실행 하 고 해당 중단점의 조건을 충족 하는 첫 번째 역할 인스턴스의 중단점에서 중단 됩니다. 해당 인스턴스와 해당 특정 인스턴스에 코드 줄을 실행 하 고 중단점의 조건을 충족 하는 경우에 중단점에서 멈춥니다 디버거 연결 인스턴스를 디버깅할 경우.

    ![디버거 연결](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746719.gif)

3. 인스턴스에 디버거를 후 평소 처럼 디버그 합니다. 디버거는 자동으로 사용자의 역할에 대 한 적절 한 호스트 프로세스에 연결합니다. 역할에 따라 디버거에서 w3wp.exe, WaWorkerHost.exe 또는 WaIISHost.exe에 연결 합니다. 디버거가 연결 되어 있는 프로세스를 확인 하려면 서버 탐색기에서 인스턴스 노드를 확장 합니다. 참조 [Azure 역할 아키텍처](http://blogs.msdn.com/b/kwill/archive/2011/05/05/windows-azure-role-architecture.aspx) Azure 프로세스에 대 한 자세한 내용은 합니다.

    ![코드 형식 선택 대화 상자](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718346.png)

4. 디버거가 연결 되어 있는 프로세스를 식별 하려면 메뉴 모음의 디버그, Windows, 프로세스를 선택 하 여, 프로세스 대화 상자를 엽니다. (키보드: Ctrl + Alt + Z) 특정 프로세스를 분리 하려면 해당 바로 가기 메뉴를 열고 선택한 **프로세스 분리**합니다. 또는 서버 탐색기에서 인스턴스 노드를 찾을, 프로세스, 해당 바로 가기 메뉴를 연 및 선택한 **프로세스 분리**합니다.

    ![프로세스 디버깅](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC690787.gif)

> [!WARNING]
> 원격 시 중단점에서 장시간 중지 하지 않도록 디버깅 합니다. Azure에 대 한 응답으로 몇 분 이상 중지 되 고 해당 인스턴스로 트래픽 전송을 중지 하는 프로세스를 처리 합니다. 너무 오랫동안 중지 하는 경우 msvsmon.exe 프로세스에서 분리 됩니다.

인스턴스나 역할의 모든 프로세스에서 디버거를 분리 하려면 디버깅 하 고 다음을 선택 하는 인스턴스나 역할에 대 한 바로 가기 메뉴를 연 **디버거 분리**합니다.

## <a name="limitations-of-remote-debugging-in-azure"></a>Azure에서 원격 디버깅의 제한 사항

Azure SDK 2.3의 원격 디버깅에 다음과 같은 제한 사항이 있습니다.

* 원격 디버깅 사용, 사용 하 여 모든 역할에 25 개 이상의 인스턴스가 클라우드 서비스를 게시할 수 없습니다.
* 디버거는 30400에서 30424, 31400에서 31424 및 32400에서 32424의 포트를 사용합니다. 이러한 포트 중 하나를 사용 하려는 경우, 서비스를 게시할 수 없습니다 하 고 다음 오류 메시지 중 하나가 azure 활동 로그에 표시 됩니다.

  * .Csdef 파일에 대해.cscfg 파일의 유효성 검사 오류가 발생 했습니다.
    끝점에 대 한 예약 된 포트 범위 '범위' 역할의 Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector에서 이미 정의 된 포트 또는 범위와 겹칩니다.
  * Allocation failed. 나중에 다시 시도, VM 크기 또는 역할 인스턴스의 수를 줄여 보십시오 하거나 다른 지역에 배포를 시도 하세요.

## <a name="debugging-azure-virtual-machines"></a>Azure 가상 머신을 디버깅

Visual Studio에서 서버 탐색기를 사용 하 여 Azure virtual machines에서 실행 되는 프로그램을 디버깅할 수 있습니다. Azure 가상 머신에서 원격 디버깅을 사용 하면 Azure 가상 머신에서 원격 디버깅 확장을 설치 합니다. 그런 다음 가상 컴퓨터의 프로세스에 연결 하 고 평소 대로 디버그할 수 있습니다.

> [!NOTE]
> Visual Studio 2015에서 클라우드 탐색기를 사용 하 여 Azure 리소스 관리자 스택을 통해 만든 가상 컴퓨터를 원격으로 디버그할 수 있습니다. 자세한 내용은 [클라우드 탐색기를 사용 하 여 Azure 리소스 관리](http://go.microsoft.com/fwlink/?LinkId=623031)합니다.

### <a name="to-debug-an-azure-virtual-machine"></a>Azure 가상 컴퓨터를 디버깅 하려면

1. 서버 탐색기에서 Virtual Machines 노드를 확장 하 고 디버그 하려는 가상 컴퓨터의 노드를 선택 합니다.

2. 상황에 맞는 메뉴를 열고 선택 **디버깅 사용**합니다. 면 선택 된 가상 컴퓨터에서 디버깅을 사용 하도록 설정 하려는 경우 확인 메시지가 표시 되 면 **예**합니다.

    Azure 디버깅을 사용 하려면 가상 머신에서 원격 디버깅 확장을 설치 합니다.

    ![가상 머신 디버깅 사용 명령](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746720.png)

    ![Azure 활동 로그](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746721.png)

3. 원격 디버깅 확장 설치가 끝나면, 가상 컴퓨터의 상황에 맞는 메뉴를 열고 선택 **디버거 연결...**

    Azure 가상 머신에서 프로세스 목록을 가져옵니다 하 고 처리 대화 상자에 연결 합니다.

    ![디버거 연결 명령](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746722.png)

4. 에 **프로세스에 연결** 대화 상자에서 **선택** 디버그 하려는 코드 형식만 표시 하도록 결과 목록을 제한 합니다. 32 비트 또는 64 비트 관리 코드, 네이티브 코드 또는 둘 다 디버그할 수 있습니다.

    ![코드 형식 선택 대화 상자](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718346.png)

5. 가상 컴퓨터에서 디버그 하 고 선택한 프로세스 선택 **연결**합니다. 예를 들어, 가상 컴퓨터에서 웹 앱을 디버그 하려면 w3wp.exe 프로세스를 선택할 수 있습니다. 참조 [디버그 하나 이상의 Visual Studio에서 프로세스](https://msdn.microsoft.com/library/jj919165.aspx) 하 고 [Azure 역할 아키텍처](http://blogs.msdn.com/b/kwill/archive/2011/05/05/windows-azure-role-architecture.aspx) 자세한 내용은 합니다.

## <a name="create-a-web-project-and-a-virtual-machine-for-debugging"></a>웹 프로젝트 및 디버깅을 위한 가상 컴퓨터 만들기

Azure 프로젝트를 게시 하기 전에 수 찾게 디버깅 및 테스트 시나리오를 지원 하 고 테스트 및 모니터링 프로그램을 설치할 수 있는 포함 된 환경에서 테스트 하는 데 유용 합니다. 이러한 테스트를 실행 하는 한 가지 방법은 가상 머신에서 앱을 원격으로 디버그 하는 경우

Visual Studio ASP.NET 프로젝트에는 앱 테스트를 위해 사용할 수 있는 편리한 가상 머신을 만드는 옵션을 제공 합니다. 가상 머신은 PowerShell, 원격 데스크톱 및 WebDeploy와 같은 일반적으로 필요한 끝점을 포함 합니다.

### <a name="to-create-a-web-project-and-a-virtual-machine-for-debugging"></a>웹 프로젝트를 만들고 디버깅을 위한 가상 컴퓨터

1. Visual Studio에서 새 ASP.NET 웹 응용 프로그램을 만듭니다.

2. 새 ASP.NET 프로젝트 대화 상자의 Azure 섹션에서에서 선택 **가상 머신** 드롭다운 목록 상자에서. 유지 된 **원격 리소스 만들기** 확인란을 선택 합니다. 선택 **확인** 진행 합니다.

    합니다 **Azure에 가상 머신을 만드는** 대화 상자가 나타납니다.

    ![ASP.NET 웹 프로젝트 만들기 대화 상자](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746723.png)

    **참고:** 로그인 아직 없는 경우 Azure 계정에 로그인 하 라는 메시지가 나타납니다.

3. 가상 컴퓨터에 대 한 다양 한 설정을 선택 하 고 선택한 **확인**합니다. 참조 [가상 머신](http://go.microsoft.com/fwlink/?LinkId=623033) 자세한 내용은 합니다.

    DNS 이름에 대해 입력 한 이름이 가상 컴퓨터의 이름이 됩니다.

    ![Azure 대화 상자에서 가상 머신 만들기](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746724.png)

    Azure 가상 머신 및 다음 프로 비전 만들고 원격 데스크톱 및 웹 배포와 같은 끝점을 구성 합니다.

4. 가상 컴퓨터를 완전히 구성한 후 서버 탐색기에서 가상 컴퓨터의 노드를 선택 합니다.

5. 상황에 맞는 메뉴를 열고 선택 **디버깅 사용**합니다. 면 선택 된 가상 컴퓨터에서 디버깅을 사용 하도록 설정 하려는 경우 확인 메시지가 표시 되 면 **예**합니다.

    Azure 디버깅을 사용 하려면 가상 머신에 원격 디버깅 확장을 설치 합니다.

    ![가상 머신 디버깅 사용 명령](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746720.png)

    ![Azure 활동 로그](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746721.png)

6. 에 설명 된 대로 프로젝트를 게시 [방법: 게시 웹 배포 프로젝트를 사용 하 여 한 번의 클릭 Visual Studio에서](https://msdn.microsoft.com/library/dd465337.aspx)합니다. 가상 컴퓨터에서 디버그 하려고 하기 때문에 **설정을** 페이지의 **웹 게시** 마법사 **디버그** 구성으로 합니다. 따라서 디버깅 하는 동안 코드 기호를 사용할 수 있도록 합니다.

    ![게시 설정](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718349.png)

7. 에 **파일 게시 옵션**를 선택 **대상에서 추가 파일 제거** 프로젝트는 이전에 이미 배포 된 경우.

8. 서버 탐색기에서 가상 컴퓨터의 상황에 맞는 메뉴에서 프로젝트를 게시 한 후 선택 **디버거 연결...**

    Azure 가상 머신에서 프로세스 목록을 가져옵니다 하 고 처리 대화 상자에 연결 합니다.

    ![디버거 연결 명령](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746722.png)

9. 에 **프로세스에 연결** 대화 상자에서 **선택** 디버그 하려는 코드 형식만 표시 하도록 결과 목록을 제한 합니다. 32 비트 또는 64 비트 관리 코드, 네이티브 코드 또는 둘 다 디버그할 수 있습니다.

    ![코드 형식 선택 대화 상자](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718346.png)

10. 가상 컴퓨터에서 디버그 하 고 선택한 프로세스 선택 **연결**합니다. 예를 들어, 가상 컴퓨터에서 웹 앱을 디버그 하려면 w3wp.exe 프로세스를 선택할 수 있습니다. 참조 [디버그 하나 이상의 Visual Studio에서 프로세스](https://msdn.microsoft.com/library/jj919165.aspx) 자세한 내용은 합니다.

## <a name="next-steps"></a>다음 단계

* 사용 하 여 **Intellitrace** 릴리스 서버에서 호출 및 이벤트 로그를 수집 하도록 합니다. 참조 [IntelliTrace 및 Visual Studio를 사용 하 여 게시 된 클라우드 서비스 디버깅](http://go.microsoft.com/fwlink/?LinkID=623016)합니다.

* 사용 하 여 **Azure 진단** 개발 환경에서 또는 Azure에서 실행 되는 역할 내에서 실행 되는 코드에서 자세한 정보를 기록 합니다. 참조 [Azure 진단을 사용 하 여 로깅 데이터 수집](http://go.microsoft.com/fwlink/p/?LinkId=400450)합니다.
