---
title: Visual Studio 디버거를 사용 하 여 디버그 하는 방법을 알아봅니다
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 06/15/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1144e7e33709510cb03ed02cb62020f81e8e8b62
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36303148"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>자습서: Visual Studio를 사용 하 여 디버그 하는 방법을 알아봅니다

이 항목에서는 단계별 연습에서는 Visual Studio 디버거 기능을 소개 합니다. 디버거 기능 상위 수준의 뷰를 원한다 면 참조 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)합니다. 경우 있습니다 *앱을 디버그*, 디버거가 연결 된 응용 프로그램을 실행 하는 일반적으로 의미 합니다. 디버거는 코드 수행 하는 참조 하는 방법은 많습니다 제공 이렇게 하면 실행 중입니다. 코드를 단계별로 실행 하 고 변수에 저장 된 값을 살펴보고, 조사식 변수 값을 변경 하는 경우 참조를 설정할 수 있습니다, 코드의 실행 경로 확인할 수 있습니다 et al. 읽을 하려는 처음 코드를 디버그 하려는 경우 [초보자를 위한 디버깅](../debugger/debugging-absolute-beginners.md) 이 항목을 진행 하기 전에 합니다.

디버거의 기능 확인에 따라 하거나 읽을 수 있습니다 하거나 기능 둘러보기에 사용 되는 전체 샘플을 다운로드 하 고 단계를 수행 합니다. 샘플을 다운로드 하 고 과정을 따르려면로 이동 [사진 뷰어 데모](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a)합니다.

|         |         |
|---------|---------|
|  ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기")  |    [비디오를 시청](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171) 비슷한 단계를 보여 주는 디버깅 합니다. |

데모 앱은 C#, 기능은 c + +, Visual Basic, JavaScript 및 Visual Studio (언급 한 위치 제외) 지 원하는 다른 언어에 적용할 수 있습니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 디버거를 시작 하 고 중단점을 적중 합니다.
> * 디버거에서 코드를에서 단계별로 실행 하려면 명령에 알아보기
> * 데이터 팁 및 디버거 창에서 변수 검사
> * 호출 스택을 검사합니다
> * 예외 도우미 사용

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017이 설치 되어 있어야 하며 합니다. **NET 데스크톱 개발** 워크 로드.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

    워크로드를 설치해야 하지만 이미 Visual Studio가 있는 경우 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다(**파일** > **새로 만들기** > **프로젝트**를 선택합니다). Visual Studio 설치 관리자가 시작됩니다. 선택 합니다. **NET 데스크톱 개발** 워크 로드를 선택한 **수정**합니다.

## <a name="start-the-debugger"></a>디버거를 시작 합니다!

1. Visual Studio에서 다음이 단계를 진행 하는 샘플을 다운로드 [이 페이지에서](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a)합니다.

    > [!IMPORTANT]
    > 데모에서 사용 하 여 앱을 실행 하려면.NET 데스크톱 개발 워크 로드를 사용 하 여 Visual Studio를 설치 해야 합니다.

2. 프로젝트를 압축을 풉니다.

3. Visual Studio를 열고 선택 합니다 **파일 > 열기** 메뉴 명령을 선택한 **프로젝트/솔루션**, 다음 프로젝트를 다운로드 한 폴더를 엽니다.

     ![샘플 프로젝트를 엽니다](../debugger/media/dbg-tour-open-project.png "프로젝트 열기")

3. WPF 사진 뷰어 데모를 열고 > C# 폴더를 선택 합니다 *photoapp.sln* 파일을 선택한 **열기**합니다.

     프로젝트는 Visual Studio에서 열립니다. 솔루션 탐색기 오른쪽 창에서 모든 프로젝트 파일 보여 줍니다.

    ![솔루션 탐색기 파일](../debugger/media/dbg-tour-solution-explorer.png "솔루션 탐색기")

4. 키를 눌러 **F5** (**디버그 > 디버깅 시작**) 또는 **디버깅 시작** 단추 ![디버깅 시작](../debugger/media/dbg-tour-start-debugging.png "디버깅 시작 ") 디버그 도구 모음에서 합니다.

     ![사진 뷰어 앱](../debugger/media/dbg-tour-wpf-app.png "사진 뷰어 앱")

     F5는 디버거가 중단점을 추가 또는 코드를 검사 하기 위해 특별히 수행 하지 않은에서는 이제 앱 프로세스 하지만 오른쪽 연결 된 앱을 시작 합니다. 앱만 있으므로 로드 하 고 사진 이미지를 참조 하세요.

     이 자습서에서는 디버거를 사용 하 여이 앱에 자세히 살펴보겠습니다 고 살펴보세요 디버거 기능 됩니다.

5. 빨간색 중지 키를 눌러 디버거를 중지 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 단추입니다.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점을 설정 하 고 디버거를 시작

을 디버깅 하려면 디버거가 응용 프로그램 프로세스에 연결 된 앱을 시작 해야 합니다.

1. 에 `MainWindow` MainWindow.xaml.cs의 생성자 코드의 첫 번째 줄의 왼쪽된 여백을 클릭 하 여 중단점을 설정 합니다.

     ![중단점을 설정](../debugger/media/dbg-tour-set-a-breakpoint.gif "SetABreakPoint")

    중단점은 신뢰할 수 있는 디버깅의 가장 기본적이 고 필수적인 기능입니다. 중단점은 변수의 값, 메모리의 동작 또는 코드 분기의 실행 여부를 확인할 수 있도록 Visual Studio에서 실행 중인 코드를 일시 중단해야 하는 위치를 나타냅니다. 

6. 키를 눌러 **F5** 또는 **디버깅 시작** 앱 시작 단추 및 디버거에서 중단점을 설정한 코드 줄을 실행 합니다.

    노란색 화살표는도 동일한 지점 (이 문에 아직 실행)에서 앱 실행을 일시 중단 되는 디버거가 일시 중지, 문을 나타냅니다.

    F5 계속 다음 중단점까지 앱을 실행 합니다. (앱이 아직 실행 되지 경우 F5 디버거를 시작 및 첫 번째 중단점에서 중지 됩니다.)

    중단점은 코드의 줄 또는 자세히 검사 하려는 코드 부분을 알고 있는 경우는 유용한 기능입니다.

## <a name="optional-restart-your-app-quickly"></a>(선택 사항) 앱을 신속 하 게 다시 시작

클릭 합니다 **다시 시작** ![앱 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 디버그 도구 모음에서 단추 (**Ctrl** + **Shift**   +  **F5**).

누르면 **다시 시작**, 앱을 중지 하 고 디버거를 다시 시작 및 시간을 절약 합니다. 코드를 실행 하 여 적중 되는 첫 번째 중단점에서 디버거가 일시 중지 합니다.

에 설정한 중단점에서 디버거를 다시 중지는 `MainWindow` 생성자입니다.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>단계 명령을 사용 하 여 디버거에서 코드를 이동 합니다.

주로 사용 하 여 바로 가기 키를 여기에서 얻을 수는 좋은 방법 이기 때문에 (해당 하는 등의 명령 메뉴 명령을 괄호 안에 표시 됩니다) 디버거에서 앱 실행 시 빠른 합니다.

1. 키를 눌러 **F11** (**디버그 > 한 단계씩 코드 실행**) 앱의 실행을 두 번의 `InitializeComponent()` 함수입니다.

     ![F11 키를 한 단계씩 코드 실행 코드 사용](../debugger/media/dbg-tour-f11.png "F11 한 단계씩 코드 실행")

     F11은는 **한 단계씩 코드 실행** 명령 및 한 번에 앱 실행 하나의 문 앞으로 이동 합니다. F11이 대부분의 정보에 실행 흐름을 검사 하는 것이 좋습니다. (이동할 더 빠르게 코드를 통해 살펴보겠습니다 몇 가지 다른 옵션 또한.) 기본적으로 디버거를 건너뜁니다 사용자 코드가 아닌 (자세한 정보를 원하는 경우 참조 [Just My Code](../debugger/just-my-code.md)).

     >[!NOTE]
     > 관리 코드에서 속성 및 연산자 건너뛰기 (기본 동작) 자동으로 실행 될 때 알림을 받을 것인지 묻는 대화 상자가 표시 됩니다. 설정을 변경 하려는 경우 나중에 사용 하지 않도록 설정 **속성 및 연산자 건너뛰기** 에서 설정 된 **도구 > 옵션** 아래에 있는 메뉴 **디버깅**합니다.

2. 키를 눌러 **F10** (**디버그 > 프로시저 단위 실행**)를 여러 번 중지 될 때까지 디버거가 코드의 첫 번째 줄에는 `OnApplicationStartup` 이벤트 처리기입니다.

     ![F10 프로시저 단위 실행 코드를 사용 하 여](../debugger/media/dbg-tour-f10-step-over.png "F10 프로시저 단위 실행")

     F10 함수나 (코드가 계속 실행) 앱 코드에서 메서드를 한 단계씩 실행 하지 않고 디버거를 이동 합니다. F10 키를 눌러 합니다 `InitializeComponent` 메서드 호출 (대신 F11)에서는 건너뜁니다에 대 한 구현 코드 `InitializeComponent` (우리는 관심이 지금는 maybe).

## <a name="step-into-a-property"></a>속성으로 단계

1. 디버거를 사용 하 여이 코드 줄에서 일시 중지 합니다.

    ````c#
    mainWindow.Photos.Path = Environment.CurrentDirectory + "\\images";
    ````

    선택한 코드 줄을 마우스 오른쪽 단추로 클릭 **단계씩**, 다음 **SDKSamples.ImageSample.PhotoCollection.Path.set**

     ![특정 기능에 대 한 단계를 사용 하 여](../debugger/media/dbg-tour-step-into-specific.png "단계씩")

    디버거 관리 되는 속성 및 필드를 건너뜁니다 기본적으로 앞서 설명한 대로 하지만 **단계씩** 명령을이 동작을 재정의할 수 있습니다. 이제 결과 확인 하려는 경우는 `Path.set` 속성 setter 실행 합니다. **한 단계씩** 를 가져옵니다는 `Path.set` 여기에 코드를 합니다.

     ![Step into Specific 결과인](../debugger/media/dbg-tour-step-into-specific-2.png "단계씩")

     `Update` 흥미로울 수 있습니다이 코드의 메서드로 같습니다 디버거는 코드를 자세히 검사를 사용 하는 그럴 수 있습니다.

5. 마우스로 합니다 `Update` 녹색까지 메서드 **실행 하려면 클릭** 단추 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 왼쪽에 표시 됩니다.

     ![실행 하려면 클릭을 사용 하 여 기능](../debugger/media/dbg-tour-run-to-click-2.png "실행 하려면 클릭")

    >  [!NOTE]
    > 합니다 **실행 하려면 클릭** 단추에서 새로운 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다. 녹색 화살표 단추를 보이지 않으면 대신 F11이이 예제에서 디버거를 진행 합니다.

6. 클릭 합니다 **실행 하려면 클릭** 단추 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick")합니다.

    이 단추를 사용 하는 것은 임시 중단점을 설정 하는 것과 비슷합니다. **실행 하려면 클릭** (열려 있는 특정 파일에서 클릭 수)는 앱 코드의 표시 영역 내에서 신속 하 게 살펴보기에 유용 합니다.

    디버거를 이동 합니다 `Update` 메서드 구현 합니다.

7. 키를 눌러 **F11** 한 단계씩 실행 하는 `Update` 메서드.

     ![Update 메서드를 한 단계씩 실행 결과](../debugger/media/dbg-tour-update-method.png "단계에 Update 메서드")

    흥미로운; 보이는 몇 가지 더 많은 코드를 알게 여기, 앱은 모든 연결입니다. *jpg* 특정 디렉터리에 있는 한 다음 각 파일에 대 한 사진 개체를 만드는 파일입니다. 이 코드에서는 디버거를 사용 하 여 앱 상태 (변수)을 검사 하려면 수 있는 좋은 기회를 제공 합니다. 이 자습서의 다음 섹션에는 보여드리겠습니다.

    변수를 검사할 수 있도록 하는 기능은 디버거에서의 가장 유용한 기능 중 하나 및 작업을 수행 하는 방법은 여러 가지입니다. 종종 문제를 디버깅 하려고 할 때 변수 값으로 특정 시간에 예상 되는 저장 하는 여부를 확인 하려고 합니다.

## <a name="examine-the-call-stack"></a>호출 스택을 검사합니다

일시 중지 된 동안 합니다 `Update` 메서드를 클릭 합니다 **호출 스택** 기본적으로 오른쪽 아래 창에 열려 있는 창을 합니다.

![호출 스택을 검사할](../debugger/media/dbg-tour-call-stack.png "ExamineCallStack")

합니다 **호출 스택** 창 있는 메서드 및 함수는 호출 되는 순서를 보여 줍니다. 맨 위 줄 현재 함수를 보여 줍니다 (의 `Update` 둘러보기 앱에서 메서드). 두 번째 줄에 따르면 `Update` 에서 호출한는 `Path.set` 속성과 등입니다.

>  [!NOTE]
> 합니다 **호출 스택** Eclipse와 같은 일부 Ide 창에 디버그 관점 비슷합니다.

호출 스택은 좋은 점검 하 여 앱의 실행 흐름을 이해 합니다.

해당 소스 코드를 살펴볼 코드 줄을 두 번 클릭 수 및 디버거에 의해 검사 되 고 현재 범위를 변경 하는 합니다. 이 그러면 디버거를 진행 하지 않습니다.

오른쪽 클릭 메뉴에서 사용할 수도 있습니다는 **호출 스택** 다른 작업을 수행 하는 창입니다. 예를 들어, 있습니다 지정 된 함수에 중단점을 삽입을 사용 하 여 디버거를 계속 진행 **커서까지 실행**, 이동한 소스 코드를 검사 합니다. 자세한 내용은 [방법: 호출 스택 검사](../debugger/how-to-use-the-call-stack-window.md)합니다.

## <a name="step-out"></a>프로시저 나가기

완료 되는 경우를 가정해 검사는 `Update` 메서드 Data.cs에서 함수의 가져오지만 디버거에서 유지 하려고 합니다. 사용 하 여 수행할 수 있습니다 합니다 **프로시저 나가기** 명령입니다.

1. 키를 눌러 **Shift** + **F11** (또는 **디버그 > 프로시저 나가기**).

     앱 실행을 다시 시작 (및 디버거 이동)이이 명령은 현재 함수가 반환 될 때까지 합니다.

     다시 해야는 `Update` Data.cs에서 메서드를 호출 합니다.

2. 키를 눌러 **Shift** + **F11** 마찬가지로 디버거 호출 스택 위로 이동 하 고 다시는 `OnApplicationStartup` 이벤트 처리기입니다.

## <a name="run-to-cursor"></a>커서까지 실행

1. 선택 된 **디버깅 중지** 빨간색 단추 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 하거나 **Shift** + **F5** .

2. 에 `Update` 에서 메서드 *Data.cs*를 마우스 오른쪽 단추로 클릭 합니다 `Add` 메서드를 호출 하 고 선택 **커서까지 실행**. 이 명령은 디버깅을 시작 하 고 코드의 현재 줄에 임시 중단점을 설정 합니다.

     ![실행 커서 기능을 사용 하 여](../debugger/media/dbg-tour-run-to-cursor.png "커서까지 실행")

    중단점에서 일시 중지 해야 `MainWindow` (첫 번째 중단점 이므로 설정한).

3. 키를 눌러 **F5** 이동 합니다 `Add` 선택 하는 메서드 **커서까지 실행**합니다.

    이 명령은 코드를 편집할 때 신속 하 게 임시 중단점을 설정 하 고 디버거를 시작 하려는 경우 유용 합니다.

## <a name="change-the-execution-flow"></a>실행 흐름 변경

1. 디버거가 일시 중지 된 상태에 `Add` 메서드 호출 (실행 포인터)의 노란색 화살표를 끌어 마우스를 사용 하 여 왼쪽 및 노란색 화살표를 한 줄 위로 이동 하는 `foreach` 루프입니다.

     ![실행 포인터를 이동](../debugger/media/dbg-tour-move-the-execution-pointer.gif "실행 포인터를 이동 합니다.")

    실행 흐름을 변경 하면 다른 코드 실행 경로 테스트 하거나 디버거를 다시 시작 하지 않고 코드를 다시 실행 하는 등 작업을 수행할 수 있습니다.

2. 이제 키를 눌러 **F5**합니다.

    앱 창에 추가한 이미지를 볼 수 있습니다. 때문에 코드를 다시 실행 하 여 `foreach` 이미지 중 일부를 루프를 두 번 추가 되었습니다!

    > [!WARNING]
    > 이 기능을 사용 하 여 주의 해야 하는 경우가 많습니다 및 도구 설명에 경고를 표시 합니다. 다른 경고를 너무 표시 될 수 있습니다. 포인터를 이동 하면 응용 프로그램을 이전 앱 상태를 되돌릴 수 없습니다.

## <a name="inspect-variables-with-data-tips"></a>데이터 팁을 사용 하 여 변수를 검사 합니다.

1. 오픈 *Data.cs* 사진 뷰어 데모 앱에서 마우스 오른쪽 단추로 클릭 합니다 `private void Update` 함수 선언 및 선택 **커서까지 실행** (앱 중지 먼저 이미 실행 중인 경우).

    디버거가 연결 된 앱을 멈춥니다. 이 속성을 사용 하면 해당 상태를 검사할 수 있습니다.

2. 마우스로 합니다 `Add` 메서드 호출을 클릭 합니다 **실행 하려면 클릭** 단추 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick")합니다.

3. 이제 파일 개체를 마우스로 (`f`)의 기본 속성 값, 파일 이름을 표시 하 고 *031. jpg 시장*합니다.

     ![데이터 팁을 보려면](../debugger/media/dbg-tour-data-tips.gif "데이터 팁 보기")

4. 개체와 같은 속성은 모두를 확장 하 고는 `FullPath` 속성입니다.

    종종를 디버깅할 때 개체에 대 한 속성 값을 확인 하는 빠른 방법 및 데이터 팁은 작업을 수행 하는 좋은 방법입니다.

    > [!TIP]
    > 대부분의 지원 되는 언어로 변경 하려는 것이 있으면 디버거 세션 중에 코드를 편집할 수 있습니다. 자세한 내용은 참조 하세요. [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다. 그러나이 앱에서 해당 기능을 사용 하려면 먼저 해야.NET framework 앱의 버전을 업데이트 합니다.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>자동 및 지역 창을 사용 하 여 변수를 검사 합니다.

1. 확인 합니다 **자동** 코드 편집기의 맨 아래에 있는 창입니다.

     ![자동 창에서 변수를 검사할](../debugger/media/dbg-tour-autos-window.png "자동 창")

    에 **자동** 창 변수와 해당 현재 값을 표시 합니다. 합니다 **자동** 창에 현재 줄 이나 이전 줄에 사용 되는 모든 변수 표시 (c + +, 창에는 표시 변수 이전 세 줄의 코드만으로 합니다. 언어별 동작에 대 한 설명서를 참조).

    > [!NOTE]
    > JavaScript에는 **지역** 창이 아닌 지원 되는 **자동** 창.

2. 다음을 확인 하는 **지역** 창입니다.

    합니다 **지역** 창에서는 현재 범위에 있는 변수를 보여 줍니다.

    ![지역 창에서 변수를 검사할](../debugger/media/dbg-tour-locals-window.png "지역 창")

    현재는 `this` 개체와 파일 (`f`) 현재 범위에 있습니다. 자세한 내용은 참조 하세요. [자동 및 지역 Windows에서 변수 검사](../debugger/autos-and-locals-windows.md)합니다.

## <a name="set-a-watch"></a>조사식 설정

1. 기본 코드 편집기 창에서 마우스 오른쪽 단추로 클릭 된 파일 개체 (`f`) 선택 **조사식 추가**합니다.

    사용할 수는 **조사식** 창에서 변수 (또는 식을) 주시 하려는 지정 합니다.

    이제 설정 조사식은 `File` 개체, 디버거를 통해 이동할 때 변경 해당 값을 볼 수 있습니다. 다른 변수 창과 달리 합니다 **조사식** 창 항상 표시 변수 조사 중인 (해당 하는 회색으로 표시 될 때 범위를 벗어납니다).

2. 에 `Add` 메서드를 녹색 클릭 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 단추를 다시 (또는 몇 번 F11 키를 눌러)를 이동할를 `foreach` 루프입니다.

    ![변수에 조사식 설정](../debugger/media/dbg-tour-watch-window.png "조사식 창")

    실행 하는의 주 창에 추가 하는 첫 번째 그림 나타날 이미지 수 표시 되지 않도록 아직 있지만 샘플 앱에서 다른 앱 스레드에서 발생 합니다.

    자세한 내용은 참조 하세요. [조사식 및 간략 한 조사식 Windows를 사용 하 여 조사식 설정](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-an-exception"></a>예외를 검사 합니다.

1. 실행 중인 앱 창에서 텍스트를 삭제 합니다 **경로** 입력란을 선택 합니다 **변경** 단추입니다.

     ![예외가 throw](../debugger/media/dbg-tour-cause-an-exception.png "예외가 발생 합니다.")

     앱에서 예외를 throw 하 고 디버거에서 예외를 발생 시킨 코드 줄으로 이동 합니다.

     ![예외 도우미](../debugger/media/dbg-tour-exception-helper.png "예외 도우미")

     여기에 **예외 도우미** 보여 줍니다는 `System.ArgumentException` 및 경로 올바른 형식이 아닙니다 되었다는 오류 메시지. 따라서 메서드 또는 함수의 인수에 오류가 발생 한 알고 있습니다.

     이 예제는 `DirectoryInfo` 호출에 저장 된 빈 문자열에 오류를 지정한는 `value` 변수입니다. (마우스로 `value` 빈 문자열을 확인 합니다.)

     예외 도우미에는 오류를 디버깅할 수 있는 훌륭한 기능입니다. 오류 세부 정보 보기와 같은 작업을 수행 하 고 예외 도우미에서 조사식을 추가할 수도 있습니다. 또는 필요한 경우 특정 예외를 throw 하는 것에 대 한 조건을 변경할 수 있습니다.

    >  [!NOTE]
    > 예외 도우미에 예외 도우미 대체 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.

2. 확장 된 **예외 설정** 수 있지만이 예외 형식을 처리 하는 방법에 대 한 다른 옵션을 보려면 노드를이 살펴보기 위해 아무 것도 변경할 필요가 없습니다!

3. 앱을 계속하려면 **F5** 키를 누릅니다.

디버거의 기능에 대 한 자세한 내용은 참조 하세요 [디버거 팁과 요령](../debugger/debugger-tips-and-tricks.md)합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 디버거를 시작 하면 코드를 단계별로 실행 하 여 변수를 검사 하는 방법을 알아보았습니다. 자세한 정보에 대 한 링크와 함께 디버거 기능에 간략히 살펴보고 가져오려는 수 있습니다.

> [!div class="nextstepaction"]
> [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)
