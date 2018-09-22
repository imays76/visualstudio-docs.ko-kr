---
title: VS 2017에서 디버깅 시작
description: Visual Studio 디버거를 사용 하 여 응용 프로그램 디버깅 시작
ms.custom: mvc
ms.date: 06/15/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: c763d706-3213-494f-b4d2-990b6e1ec456
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2339dcfe80e994b8bc9062d137263d3b25d274d
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542418"
---
# <a name="first-look-at-the-visual-studio-debugger"></a>Visual Studio 디버거를 소개

이 항목에서는 Visual Studio에서 제공 하는 디버거 도구를 소개 합니다. Visual Studio 컨텍스트에서 경우 있습니다 *앱을 디버그*, 디버거가 연결 된 응용 프로그램을 실행 하는 일반적으로 의미 (즉, 디버거 모드에서에서). 디버거는 코드 수행 하는 참조 하는 방법은 많습니다 제공 이렇게 하면 실행 중입니다. 코드를 단계별로 실행 하 고 변수에 저장 된 값을 살펴보고, 조사식 변수 값을 변경 하는 경우 참조를 설정할 수 있습니다, 코드의 실행 경로 확인할 수 있습니다 et al. 읽을 하려는 처음 코드를 디버그 하려는 경우 [초보자를 위한 디버깅](../debugger/debugging-absolute-beginners.md) 이 항목을 진행 하기 전에 합니다.

여기에 설명 된 기능은 C#, c + +, Visual Basic, JavaScript 및 Visual Studio (언급 한 위치 제외) 지 원하는 다른 언어에 적용할 수 있습니다.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점을 설정 하 고 디버거를 시작

을 디버깅 하려면 디버거가 응용 프로그램 프로세스에 연결 된 앱을 시작 해야 합니다. **F5** (**디버그 > 디버깅 시작**) 작업을 수행 하는 가장 일반적인 방법입니다. 그러나 작업을 먼저 수행 하 고 다음 디버깅을 시작 하도록 앱을 검사할 중단점을 설정 하지 지금 코드입니다. 중단점은 신뢰할 수 있는 디버깅의 가장 기본적이 고 필수적인 기능입니다. 중단점은 변수의 값, 메모리의 동작 또는 코드 분기의 실행 여부를 확인할 수 있도록 Visual Studio에서 실행 중인 코드를 일시 중단해야 하는 위치를 나타냅니다. 

코드 편집기에서 열린 파일이 있다면 코드 줄의 왼쪽 여백을 클릭 하 여 중단점을 설정할 수 있습니다.

![중단점을 설정](../debugger/media/dbg-tour-set-a-breakpoint.gif "중단점 설정")

키를 눌러 **F5** (**디버그 > 디버깅 시작**) 또는 **디버깅 시작** 단추 ![디버깅 시작](../debugger/media/dbg-tour-start-debugging.png "디버깅 시작 ") 디버그 도구 모음에서 발견 되는 첫 번째 중단점까지 디버거 실행 합니다. 앱이 아직 실행 되지 경우 F5 디버거를 시작 하 고 첫 번째 중단점에서 중지 됩니다.

중단점은 코드의 줄 또는 자세히 검사 하려는 코드 부분을 알고 있는 경우는 유용한 기능입니다.

## <a name="navigate"></a> 단계 명령을 사용 하 여 디버거에서 코드를 이동 합니다.

앱 코드의 탐색 빠른 수 있기 때문에 대부분의 명령에 대 한 바로 가기 키를 제공 합니다. (해당 하는 명령 메뉴와 같은 명령을 괄호 안에 표시 됩니다.)

디버거가 연결 된 앱을 시작 하려면 다음을 누릅니다 **F11** (**디버그 > 한 단계씩 코드 실행**). F11은는 **한 단계씩 코드 실행** 명령 및 한 번에 앱 실행 하나의 문 앞으로 이동 합니다. F11 키를 사용 하 여 앱을 시작 하는 경우 디버거가 실행 되는 첫 번째 문에서 중단 합니다.

![F11 키를 한 단계씩](../debugger/media/dbg-tour-f11.png "F11 한 단계씩 코드 실행")

노란색 화살표는도 동일한 지점 (이 문에 아직 실행)에서 앱 실행을 일시 중단 되는 디버거가 일시 중지, 문을 나타냅니다.

F11이 대부분의 정보에 실행 흐름을 검사 하는 것이 좋습니다. (이동할 더 빠르게 코드를 통해 보여드리겠습니다 몇 가지 다른 옵션도 있습니다.) 기본적으로 디버거를 건너뜁니다 사용자 코드가 아닌 (자세한 정보를 원하는 경우 참조 [Just My Code](../debugger/just-my-code.md)).

>[!NOTE]
> 관리 코드에서 속성 및 연산자 건너뛰기 (기본 동작) 자동으로 실행 될 때 알림을 받을 것인지 묻는 대화 상자가 표시 됩니다. 설정을 변경 하려는 경우 나중에 사용 하지 않도록 설정 **속성 및 연산자 건너뛰기** 에서 설정 된 **도구 > 옵션** 아래에 있는 메뉴 **디버깅**합니다.

## <a name="step-over-code-to-skip-functions"></a>코드를 함수를 건너뛰도록 건너뛰기

줄은 함수 또는 메서드 호출 하는 코드를 사용 하는 경우 누르면 **F10** (**디버그 > 프로시저 단위 실행**) F11 대신 합니다.

F10 함수나 (코드가 계속 실행) 앱 코드에서 메서드를 한 단계씩 실행 하지 않고 디버거를 이동 합니다. F10 키를 눌러 관심이 하지 하는 코드를 건너뛸 수 있습니다. 이러한 방식으로 빠르게 확인할 수 있습니다에 더 관심이 있는 코드를 합니다.

## <a name="step-into-a-property"></a>속성으로 단계

디버거 관리 되는 속성 및 필드를 건너뜁니다 기본적으로 앞서 설명한 대로 하지만 **단계씩** 명령을이 동작을 재정의할 수 있습니다.

속성 또는 필드를 마우스 오른쪽 단추로 클릭 하 고 선택 **단계씩**, 사용 가능한 옵션 중 하나를 선택 합니다.

![특정 한 단계씩](../debugger/media/dbg-tour-step-into-specific.png "Step Into Specific")

이 예에서 **단계씩** 우리를 코드로 가져옵니다 `Path.set`합니다.

![특정 한 단계씩](../debugger/media/dbg-tour-step-into-specific-2.png "Step Into Specific")

## <a name="run-to-a-point-in-your-code-quickly-using-the-mouse"></a>신속 하 게 마우스를 사용 하 여 코드의 지점으로 실행

될 때까지 코드 줄에서 디버거를 마우스로 합니다 **실행 하려면 클릭** (여기까지 실행 실행) 단추 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 왼쪽에 표시 합니다.

![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click-2.png "실행 하려면 클릭")

> [!NOTE]
> 합니다 **실행 하려면 클릭** (여기까지 실행 실행) 단추에서 새로운 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.

클릭 합니다 **실행 하려면 클릭** (여기까지 실행 실행) 단추입니다. 디버거를 클릭 한 코드의 줄으로 이동 합니다.

이 단추를 사용 하는 것은 임시 중단점을 설정 하는 것과 비슷합니다. 이 명령은 앱 코드의 표시 영역 내에서 신속 하 게 살펴보기도 유용 합니다. 사용할 수 있습니다 **실행 하려면 클릭** 열려 있는 특정 파일에 있습니다.

## <a name="advance-the-debugger-out-of-the-current-function"></a>현재 함수에서 디버거를 진행 합니다.

경우에 따라 다음 디버깅 세션을 계속 있지만, 현재 함수가까지 디버거를 진행 하는 것이 좋습니다.

키를 눌러 **shift+f11** (또는 **디버그 > 프로시저 나가기**).

앱 실행을 다시 시작 (및 디버거 이동)이이 명령은 현재 함수가 반환 될 때까지 합니다.

## <a name="run-to-cursor"></a>커서까지 실행

키를 눌러 디버거를 중지 합니다 **디버깅 중지** 빨간색 단추 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 하거나 **Shift**  +  **F5**합니다.

선택한 앱의 코드 줄을 마우스 오른쪽 단추로 클릭 **커서까지 실행**합니다. 이 명령은 디버깅을 시작 하 고 코드의 현재 줄에 임시 중단점을 설정 합니다.

![커서까지 실행](../debugger/media/dbg-tour-run-to-cursor.png "커서까지 실행")

중단점을 설정한 경우 첫 번째 중단점에 도달 했을 디버거에서 일시 중지 됩니다.

키를 눌러 **F5** 선택 하는 코드 줄에 도달할 때까지 **커서까지 실행**합니다.

이 명령은 코드를 편집할 때 신속 하 게 임시 중단점을 설정 하 고 동시에 디버거를 시작 하려는 경우 유용 합니다.

> [!NOTE]
> 사용할 수 있습니다 **커서까지 실행** 에 **호출 스택** 디버깅 하는 동안 창입니다.

## <a name="restart-your-app-quickly"></a>앱을 신속 하 게 다시 시작

클릭 합니다 **다시 시작** ![앱 다시 시작](../debugger/media/dbg-tour-restart.png "앱 다시 시작") 디버그 도구 모음에서 단추 (**Ctrl + Shift + F5**).

누르면 **다시 시작**, 앱을 중지 하 고 디버거를 다시 시작 및 시간을 절약 합니다. 코드를 실행 하 여 적중 되는 첫 번째 중단점에서 디버거가 일시 중지 합니다.

빨간색 중지를 수행 하려는 경우 디버거를 중지 하 고 코드 편집기에 다시 접속을 눌러도 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 단추 대신 **를 다시 시작**합니다.

## <a name="inspect-variables-with-data-tips"></a>데이터 팁을 사용 하 여 변수를 검사 합니다.

이제 잠시 둘러보면을 알고 있다고 디버거를 사용 하 여 앱 상태 (변수) 검사를 시작 하기에 좋은 시점입니다. 변수를 검사할 수 있도록 하는 기능은 디버거에서의 가장 유용한 기능 중 일부와 작업을 수행 하는 방법은 여러 가지입니다. 종종 문제를 디버깅 하려고 할 때 변수 값이 예상 대로 특정 앱 상태에 저장 하는 여부를 확인 하려고 합니다.

디버거에서 일시 중지 하는 동안 마우스를 사용 하 여 개체를 가리키면 해당 기본 속성 값을 표시 하 고 (이 예제에서는 파일 이름 `market 031.jpg` 는 기본 속성 값).

![데이터 팁을 보려면](../debugger/media/dbg-tour-data-tips.gif "데이터 팁 보기")

개체 속성은 모두를 확장 하 고 (같은 `FullPath` 이 예제의 속성).

종종를 디버깅할 때 개체에 대 한 속성 값을 확인 하는 빠른 방법 및 데이터 팁은 작업을 수행 하는 좋은 방법입니다.

> [!TIP]
> 대부분의 지원 되는 언어에서 디버깅 세션 중에 코드를 편집할 수 있습니다. 자세한 내용은 참조 하세요. [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>자동 및 지역 창을 사용 하 여 변수를 검사 합니다.

디버깅 하는 동안 확인 합니다 **자동** 코드 편집기의 아래쪽 창입니다.

![자동 창](../debugger/media/dbg-tour-autos-window.png "자동 창")

에 **자동** 변수와 함께 해당 현재 값 및 해당 형식을 표시 창입니다. 합니다 **자동** 창에 현재 줄 이나 이전 줄에 사용 되는 모든 변수 표시 (c + +, 창에는 표시 변수 이전 세 줄의 코드만으로 합니다. 언어별 동작에 대 한 설명서를 참조).

> [!NOTE]
> JavaScript에는 **지역** 창이 아닌 지원 되는 **자동** 창.

다음을 확인 하는 **지역** 창입니다. 합니다 **지역** 창에서는 현재 범위에 있는 변수를 보여 줍니다.

![지역 창](../debugger/media/dbg-tour-locals-window.png "지역 창")

이 예제에서는 합니다 `this` 개체와 개체 `f` 범위에 있습니다. 자세한 내용은 참조 하세요. [자동 및 지역 Windows에서 변수 검사](../debugger/autos-and-locals-windows.md)합니다.

## <a name="set-a-watch"></a>조사식 설정

사용할 수는 **조사식** 창에서 변수 (또는 식을) 주시 하려는 지정 합니다.

디버깅 하는 동안 개체를 마우스 오른쪽 단추로 클릭 하 고 선택 **조사식 추가**합니다.

![조사식 창](../debugger/media/dbg-tour-watch-window.png "조사식 창")

이 예제에서는 조사식 설정 해야는 `f` 개체, 디버거를 통해 이동할 때 변경 값을 볼 수 있습니다. 다른 변수 창과 달리 합니다 **조사식** windows 항상 표시 변수 조사 중인 (해당 하는 회색으로 표시 될 때 범위를 벗어납니다).

자세한 내용은 참조 하세요. [조사식 및 간략 한 조사식 Windows를 사용 하 여 조사식 설정](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-the-call-stack"></a>호출 스택을 검사합니다

클릭 합니다 **호출 스택** 기본적으로 오른쪽 아래 창에 열려 있는 창, 디버깅 중입니다.

![호출 스택을 검사할](../debugger/media/dbg-tour-call-stack.png "호출 스택을 검사")

합니다 **호출 스택** 창 있는 메서드 및 함수는 호출 되는 순서를 보여 줍니다. 맨 위 줄 현재 함수를 보여 줍니다 (의 `Update` 이 예제의 메서드). 두 번째 줄에 따르면 `Update` 에서 호출한는 `Path.set` 속성과 등입니다. 호출 스택은 좋은 점검 하 여 앱의 실행 흐름을 이해 합니다.

> [!NOTE]
> 합니다 **호출 스택** Eclipse와 같은 일부 Ide 창에 디버그 관점 비슷합니다.

해당 소스 코드를 살펴볼 코드 줄을 두 번 클릭 수 및 디버거에 의해 검사 되 고 현재 범위를 변경 하는 합니다. 이 디버거를 진행 하지 않습니다.

오른쪽 클릭 메뉴에서 사용할 수도 있습니다는 **호출 스택** 다른 작업을 수행 하는 창입니다. 특정 함수에 중단점을 삽입 하 여 앱을 다시 시작을 예를 들어 **커서까지 실행**를 이동할 소스 코드를 검사 합니다. 참조 [방법: 호출 스택을 검사](../debugger/how-to-use-the-call-stack-window.md)합니다.

## <a name="exception"></a> 예외를 검사 합니다.

앱에서 예외를 throw 하는 경우 디버거가 예외를 발생 시킨 코드 줄으로 이동 합니다.

![예외 도우미](../debugger/media/dbg-tour-exception-helper.png "예외 도우미")

이 예제에서는 **예외 도우미** 표시는 `System.Argument` 예외 및 오류 메시지는 경로 올바른 형식이 아닙니다. 따라서 메서드 또는 함수의 인수에 오류가 발생 한 알고 있습니다.

이 예제는 `DirectoryInfo` 호출에 저장 된 빈 문자열에 오류를 지정한는 `value` 변수입니다.

예외 도우미에는 오류를 디버깅할 수 있는 훌륭한 기능입니다. 오류 세부 정보 보기와 같은 작업을 수행 하 고 예외 도우미에서 조사식을 추가할 수도 있습니다. 또는 필요한 경우 특정 예외를 throw 하는 것에 대 한 조건을 변경할 수 있습니다.

>  [!NOTE]
> 예외 도우미에 예외 도우미 대체 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.

확장 된 **예외 설정** 수 있지만이 예외 형식을 처리 하는 방법에 대 한 다른 옵션을 보려면 노드를이 살펴보기 위해 아무 것도 변경할 필요가 없습니다!

## <a name="debug-live-aspnet-apps-in-azure-app-service"></a>Azure App Service에서 라이브 ASP.NET 앱 디버그

합니다 **스냅숏 디버거** 에 관심이 있는 코드가 실행 되 면 프로덕션 앱의 스냅숏을 만듭니다. 디버거가 스냅숏을 생성하도록 명령하려면 코드에서 snappoint와 logpoint를 설정합니다. 디버거를 통해 프로덕션 응용 프로그램의 트래픽에 영향을 미치지 않으면서 정확히 무엇이 잘못되었는지를 볼 수 있습니다. 스냅샷 디버거를 사용하면 프로덕션 환경에서 발생하는 문제를 해결하는 데 걸리는 시간을 상당히 줄일 수 있습니다.

![스냅숏 디버거를 시작할](../debugger/media/snapshot-launch.png "스냅숏 디버거를 시작 합니다.")

스냅숏 컬렉션은 Azure App Service에서 실행 중인 ASP.NET 응용 프로그램에서 사용할 수 있습니다. ASP.NET 응용 프로그램은.NET Framework 4.6.1에서 실행 되어야 이상 및.NET Core 2.0 또는 나중에 Windows에서 ASP.NET Core 응용 프로그램을 실행 해야 합니다.

자세한 내용은 [스냅숏 디버거를 사용 하 여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)합니다.

## <a name="view-snapshots-with-intellitrace-step-back-visual-studio-enterprise"></a>IntelliTrace 뒤로 이동 (Visual Studio Enterprise)를 사용 하 여 스냅숏 보기

**IntelliTrace 뒤로** 단계 이벤트에서 모든 중단점 및 디버거 응용 프로그램의 스냅숏을 자동으로 수행 합니다. 기록된 스냅숏을 통해 이전 중단점 또는 단계로 돌아가서 응용 프로그램의 과거 상태를 볼 수 있습니다. IntelliTrace 뒤로 이동을 사용하면 이전 응용 프로그램 상태를 보고 싶지만 디버깅을 다시 시작하거나 원하는 앱 상태를 다시 만들지 않으려는 경우에 시간을 절약할 수 있습니다.

디버그 도구 모음의 **뒤로 가기**와 **앞으로 가기** 단추를 사용하여 이동하고 스냅숏을 볼 수 있습니다. 이 단추를 사용하여 **진단 도구** 창의 **이벤트** 탭에 나타나는 이벤트를 탐색할 수 있습니다.

![단계 뒤로 및 앞으로 단추](../debugger/media/intellitrace-step-back-icons-description.png  "뒤로 및 앞으로 단추")

자세한 내용은 참조는 [IntelliTrace를 사용 하 여 이전 앱 상태를 검사](../debugger/view-historical-application-state.md) 페이지입니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 많은 디버거 기능 둘러보기 보 셨습니다. 샘플 응용 프로그램을 사용 하 여 이러한 기능을 더 자세히 살펴보려면 확인할 수 있습니다.

> [!div class="nextstepaction"]
> [Visual Studio를 사용하여 디버깅하는 자세한 내용](../debugger/getting-started-with-the-debugger.md)
