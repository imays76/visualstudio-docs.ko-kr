---
title: IntelliTrace를 사용 하 여 이전 응용 프로그램 상태 보기
ms.description: Learn how to take snapshots, and view snapshots with IntelliTrace step-back
ms.custom: mvc
ms.date: 09/19/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
ms.assetid: 7c60d929-d993-49dc-9db3-43b30be9912b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 85b34fd85e8449949bb1e96efc1dd79aacbc1bd9
ms.sourcegitcommit: 1c675dae7c348defb32d9f7ccf7079a1062a1c4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48243954"
---
# <a name="inspect-previous-app-states-using-intellitrace-step-back-in-visual-studio"></a>Visual Studio에서 IntelliTrace 뒤로 사용 하 여 이전 앱 상태를 검사 합니다.

IntelliTrace 뒤로 자동으로 모든 중단점 및 디버거에서 응용 프로그램의 스냅숏을 단계 이벤트를 만듭니다. 기록된 스냅숏을 통해 이전 중단점 또는 단계로 돌아가서 응용 프로그램의 과거 상태를 볼 수 있습니다. IntelliTrace 뒤로 이동을 사용하면 이전 응용 프로그램 상태를 보고 싶지만 디버깅을 다시 시작하거나 원하는 앱 상태를 다시 만들지 않으려는 경우에 시간을 절약할 수 있습니다.

IntelliTrace 뒤로 Visual Studio Enterprise 2017 버전 15.5 이상부터 제공 되며 Windows 10 1 주년 업데이트 필요 이상. ASP.NET, WinForms, WPF, 관리 되는 콘솔 응용 프로그램 및 관리 되는 클래스 라이브러리 디버깅에 대 한 현재 기능을 사용할 수 있습니다. Visual Studio 2017 Enterprise 버전 15.7부터 기능도 지원 됩니다 ASP.NET Core 및.NET Core 용. Visual Studio 2017 Enterprise 버전 15.9부터 기능 미리 보기 2도 지원 됩니다 Windows를 대상으로 하는 네이티브 앱. UWP 응용 프로그램을 디버깅할 현재 지원 되지 않습니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * Intellitrace 이벤트 및 스냅숏을 사용 하도록 설정
> * 뒤로 및 앞 단계 명령을 사용 하 여 이벤트를 이동 합니다.
> * 이벤트 스냅숏 보기
  
## <a name="enable-intellitrace-events-and-snapshots-mode"></a>IntelliTrace 이벤트 및 스냅숏 모드를 사용 하도록 설정 

1. Visual Studio Enterprise에서 프로젝트를 엽니다.

1. 오픈 **도구가** > **옵션** > **IntelliTrace** 설정과 옵션을 선택 **IntelliTrace 이벤트 및 스냅숏** . 

    Preview 2에서는이 옵션은 Visual Studio 2017 Enterprise 15.9 버전 부터는 **IntelliTrace 스냅숏 (관리 / 네이티브)** 합니다. 

    ![IntelliTrace 이벤트 및 스냅숏 모드를 사용 하도록 설정](../debugger/media/intellitrace-enable-snapshots.png "사용 IntelliTrace 이벤트 및 스냅숏 모드")

1. 예외에서 스냅숏 보기에 대 한 옵션을 구성 하려는 경우 선택 **IntelliTrace** > **고급** 에서 합니다 **옵션** 대화 상자.

    이러한 옵션은 Visual Studio 2017 Enterprise 버전 15.7부터 사용할 수 있습니다.

    ![예외에서 스냅숏에 대 한 동작을 구성 합니다.](../debugger/media/intellitrace-enable-snapshots-on-exceptions.png)

    이벤트 및 스냅숏을 사용 하는 경우에 예외에 대 한 스냅숏을 또한 기본적으로 사용 됩니다. 예외에서 스냅숏 선택 해제 하 여 비활성화할 수 있습니다 **예외 이벤트에 대 한 스냅숏 수집**합니다. 이 기능을 사용 하는 경우 처리 되지 않은 예외에 대 한 스냅숏이 만들어집니다. 처리 되는 예외에 대 한 스냅숏은 생성 하는 예외가 발생 하는 경우에 한 이전 throw 된 예외가 다시 throw 되지 않은 경우. 드롭다운 목록에서 값을 선택 하 여 예외에는 최대 스냅숏 수를 설정할 수 있습니다. 최대 앱 (예: 앱에 도달할 경우 중단점) 중단 모드를 시작 하는 각 시간에 적용 됩니다.

    > [!NOTE]
    > 스냅숏은 생성 하는 예외 이벤트에 대해서만 IntelliTrace 기록 합니다. 관리 코드에 대해 IntelliTrace가 기록 이벤트를 선택 하 여 지정할 수 있습니다 **도구가** > **옵션** > **IntelliTrace 이벤트**합니다.

1. 프로젝트에서 하나 이상의 중단점을 설정 하 고 디버깅 시작 (키를 눌러 **F5**), 코드를 한 단계씩 실행 하 여 디버깅을 시작 하거나 (**F10** 또는 **F11**).

    IntelliTrace는 각 디버거 단계, 중단점 이벤트 및 처리 되지 않은 예외 이벤트에서 응용 프로그램의 프로세스의 스냅숏을 만듭니다. 이러한 이벤트에 기록 됩니다 합니다 **이벤트** 탭에 **진단 도구** 다른 IntelliTrace 이벤트와 함께 창. 선택이 창을 열려면 **디버깅할** > **Windows** > **진단 도구 표시**합니다.

    카메라 아이콘 스냅숏을 사용할 이벤트 옆에 나타납니다. 

    ![스냅숏을 사용 하 여 이벤트 탭](../debugger/media/intellitrace-events-tab-with-snapshots.png "중단점 및 단계에는 스냅숏 사용 하 여 이벤트 탭")

    성능상의 이유로 하지 스냅숏을 매우 신속 하 게 실행 합니다. 카메라 아이콘이 표시 되지 않으면 단계 옆에 있는, 느리게 단계별 실행을 시도 합니다.

## <a name="navigate-and-view-snapshots"></a>이동 하 고 스냅숏 보기

1. 사용 하 여 이벤트 간을 이동할 합니다 **뒤로 (Alt + [)** 및 **앞으로 가기 (Alt +])** 디버그 도구 모음 단추입니다.

    이러한 단추에 표시 되는 이벤트를 탐색할 합니다 **이벤트** 탭에 **진단 도구 창**합니다. 활성화 이벤트 앞 이나 뒤로 자동으로 단계별 [기록 디버깅](../debugger/historical-debugging.md) 선택한 이벤트에 대 한 합니다.

    ![뒤로 및 앞으로 단추](../debugger/media/intellitrace-step-back-icons-description.png "뒤로 및 앞으로 가기 단추")

    걸음 물러나 하거나 앞으로 이동 하는 경우 Visual Studio 기록 디버깅 모드를 입력 합니다. 이 모드에서 선택한 이벤트를 기록 하는 경우에 디버거의 컨텍스트 전환 됩니다. 또한 visual Studio는 소스 창에서 코드의 해당 줄에 포인터를 이동합니다. 

    이 보기에서 값을 검사할 수 있습니다 합니다 **호출 스택**를 **지역**를 **자동**, 및 **조사식** windows. DataTips를 보고에 대 한 식 계산을 수행 하는 변수 또한 마우스로 가리키면 합니다 **직접 실행** 창입니다. 스냅숏에서 해당 시점에 수행 하는 응용 프로그램의 프로세스의 데이터가 표시 됩니다.

    따라서 예를 들어 중단점을 적중 하 고 단계를 수행 하는 경우 (**F10**), **뒤로** 단추 중단점에 해당 하는 코드의 줄에서 기록 모드로 Visual Studio를 배치 합니다. 

    ![기록 모드 스냅숏 사용 하 여 이벤트의 경우 활성](../debugger/media/intellitrace-historical-mode-with-snapshot.png "기록 모드 스냅숏 사용 하 여 이벤트의 경우 활성화 중")

2. 라이브 실행으로 돌아가려면 선택 **f5 키를 눌러 계속** 누르거나를 **라이브 디버깅으로 돌아가세요** 정보 표시줄에 링크 합니다. 

3. 스냅숏을 볼 수는 **이벤트** 탭 합니다. 이렇게 하려면 스냅숏 사용 하 여 이벤트를 선택 하 고 클릭 **기록 디버깅 활성화**합니다.

    ![이벤트 기록 디버깅을 활성화](../debugger/media/intellitrace-activate-historical-debugging.png "이벤트 기록 디버깅 활성화")

    와 달리 합니다 **다음 문 설정** 제공 응용 프로그램의 상태에 대 한 정적 뷰를 특정 시점 이전에 발생 한 시점의; 명령에서 스냅숏 보기에서 코드를 다시 실행 하지 않습니다.

    ![IntelliTrace 뒤로 개요](../debugger/media/intellitrace-step-back-overview.png "개요의 IntelliTrace 뒤로 이동")

    Visual Studio에서 변수를 검사 하는 방법에 대 한 자세한 내용은를 참조 하세요. [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)  

## <a name="frequently-asked-questions"></a>질문과 대답

#### <a name="how-is-intellitrace-step-back-different-from-intellitrace-events-only-mode"></a>IntelliTrace 뒤로 IntelliTrace 이벤트에 대 한 유일한 모드와 어떻게 다른가요?

IntelliTrace 이벤트 전용 모드에서 디버거 단계 및 중단점에서 기록 디버깅 활성화 할 수 있습니다. 그러나 IntelliTrace에서 데이터를만 캡처합니다 합니다 **지역** 및 **자동** windows 열려 있고만 확장 되는 데이터를 캡처할 경우 windows 및 보기. 이벤트 전용 모드에서 종종 없는 변수와 복잡 한 개체의 전체 보기입니다. 또한 식 평가 및 데이터 보기에는 **조사식** 창이 지원 되지 않습니다. 

IntelliTrace는 이벤트 및 스냅숏 모드에서 복잡 한 개체를 포함 하 여 응용 프로그램의 프로세스의 전체 스냅숏을 캡처합니다. 코드의 줄에 중단점에서 중지 된 (및 이전에 정보를 확장 하는 여부가 중요 하지 않은) 처럼 동일한 정보를 볼 수 있습니다. 식 계산 스냅숏을 볼 때에 지원 됩니다.  

#### <a name="what-is-the-performance-impact-of-this-feature"></a>이 기능은 성능에 영향을 무엇입니까? 

응용 프로그램에서 전체 단계별 성능에 미치는 영향에 따라 달라 집니다. 스냅숏을 만드는 오버 헤드는 약 30 ms. 스냅숏이 만들어질 때 응용 프로그램의 프로세스를 분기 하 고 분기 된 복사본을 일시 중단 됩니다. 스냅숏으로 보면 Visual Studio 프로세스의 포크 된 복사본에 연결 된입니다. 각 스냅숏에 대 한 Visual Studio 페이지 테이블에만 복사 하 고 쓰기 시 복사 페이지 설정입니다. 힙의 개체에 연결 된 스냅숏 사용 하 여 디버거 단계 사이 변경, 해당 페이지 테이블을 다음을 복사 됩니다 최소 메모리 비용이 듭니다. Visual Studio에서 스냅숏을 충분 한 메모리가 없을 있는지를 감지 하면 하나 고려 하지 않습니다.
 
## <a name="known-issues"></a>알려진 문제  
* Windows 10 Fall Creators Update (RS3) 보다 오래 된 Windows 버전에서 IntelliTrace 이벤트 및 스냅숏 모드를 사용 하는 경우 응용 프로그램의 디버그 플랫폼 대상이 x86으로 설정 된 경우 IntelliTrace 스냅숏을 사용 하지 않습니다.

    해결 방법:
    * Windows 10 1 주년 업데이트 (RS1) 10.0.14393.2273, 버전 이하의 [KB4103720 설치](https://support.microsoft.com/help/4103720/windows-10-update-kb4103720)합니다. 
    * 버전 10.0.15063.1112, 아래에서 Windows 10 크리에이터 업데이트 (RS2)에 있다면 [KB4103722 설치](https://support.microsoft.com/help/4103722/windows-10-update-4103722)합니다.
    * 설치 또는 Windows 10 Fall Creators Update (RS3)로 업그레이드 합니다. 
    * 또는: 
        1. Visual Studio 설치 관리자에서 데스크톱(x86, x64) 구성 요소용 VC++ 2015.3 v140 도구 집합을 설치합니다.
        2. 대상 응용 프로그램을 빌드합니다.
        3. 명령줄에서 editbin 도구를 사용 설정 하는 `Largeaddressaware` 대상 실행 파일에 대 한 플래그입니다. 예를 들어 (경로 업데이트) 한 후이 명령을 사용할 수 있습니다: "C:\Program Files (x86) \Microsoft Visual Studio\Preview\Enterprise\VC\Tools\MSVC\14.12.25718\bin\Hostx86\x86\editbin.exe" /Largeaddressaware "C:\Path\To\Application\app.exe"입니다.
        4. 디버깅을 시작하려면 **F5** 키를 누릅니다. 이제 디버거 단계 및 중단점에서 스냅숏은 가져옵니다.

        > [!Note]
        > `Largeaddressaware` 실행 파일 변경 하 여 다시 빌드할 때마다 플래그 설정 해야 합니다.

* 지속형된 메모리 매핑된 파일을 사용 하는 응용 프로그램에서 응용 프로그램의 프로세스는 스냅숏을 생성 하는 경우 스냅숏 사용 하 여 프로세스 (후에 부모 프로세스 잠금을 릴리스됨) 메모리 매핑된 파일에 대 한 단독 잠금을 보유 합니다. 다른 프로세스를 읽을 수 있지만 쓸, 메모리 매핑된 파일에 여전히 수 있습니다.

    해결 방법:
    * 모든 스냅숏 디버깅 세션을 종료 하 여 선택을 취소 합니다. 

* 해당 프로세스에 많은 수의 고유 메모리 영역을 많은 수의 Dll 로드 하는 응용 프로그램과 같은 응용 프로그램을 디버깅할 때 사용 하도록 설정 하는 스냅숏을 사용 하 여 성능 단계별 실행을 받을 수 있습니다. 이 문제는 Windows의 이후 버전에서 해결 될 예정입니다. 이 문제를 발생 하는 경우 연락 주시기 stepback@microsoft.com합니다. 

* 사용 하 여 파일을 저장할 때 **디버그 > IntelliTrace > 저장 IntelliTrace 세션** 이벤트 및 스냅숏 모드에서 스냅숏에서 캡처한 추가 데이터를 사용할 수 없는.itrace 파일에 있습니다. 중단점 및 단계 이벤트에서 IntelliTrace 이벤트에 대 한 전용 모드에서 파일을 저장 한 경우에 따라 동일한 정보를 참조 합니다. 

## <a name="next-steps"></a>다음 단계

이 자습서에서는 IntelliTrace 뒤로 사용 하는 방법을 알아보았습니다. 다른 IntelliTrace 기능에 자세히 알아보려면이 좋습니다.

> [!div class="nextstepaction"]
> [IntelliTrace 기능](../debugger/intellitrace-features.md)
