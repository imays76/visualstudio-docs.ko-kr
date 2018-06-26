---
title: Visual Studio 2017 개요
ms.date: 06/01/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- MSDNSTART
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a7667cac2a26a3e98d2e92dfeb13cee36d870e9
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34691162"
---
# <a name="visual-studio-ide-overview"></a>Visual Studio IDE 개요

Visual Studio IDE(대화형 개발 환경)는 코드를 보고 편집한 다음, 앱을 디버그, 빌드 및 게시하는 데 사용할 수 있는 창의적인 실행 패드입니다.

Visual Studio는 Windows 및 Mac에서 사용할 수 있습니다. [Mac용 Visual Studio](/visualstudio/mac/)에는 Visual Studio 2017과 동일한 기능이 많이 있으며 플랫폼 간 및 모바일 앱 개발을 위한 최적화되어 있습니다.

이 문서에서는 Windows용 Visual Studio 2017에 대해 중점적으로 설명합니다. IDE의 기본 기능을 소개합니다. 간단한 프로젝트 만들기, 코딩 도구로 IntelliSense 사용, 앱을 디버깅하여 프로그램 실행 중 변수 값을 확인하는 방법 등 Visual Studio로 수행할 수 있는 몇 가지 작업을 살펴보겠습니다. 또한 다양한 도구 창을 살펴보겠습니다.

## <a name="install-the-visual-studio-ide"></a>Visual Studio IDE 설치

시작하려면 [Visual Studio 2017을 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)하여 시스템에 설치합니다.

모듈식 설치 관리자를 사용하면 선호하는 프로그래밍 언어 또는 플랫폼에 필요한 기능 그룹인 *워크로드*를 선택하여 설치할 수 있습니다. [프로그램 생성](#create-a-program) 단계를 수행하려면 설치 중에 **.NET Core 플랫폼 간 개발** 워크로드를 선택해야 합니다. [Visual Studio에서 C++ 시작](getting-started-with-cpp-in-visual-studio.md)과 같은 빠른 시작 항목에는 다른 워크로드를 설치하는 방법에 대한 지침이 포함되어 있습니다.

![Visual Studio 설치 관리자](../ide/media/overview-net-core-workload.png)

Visual Studio를 처음 시작하면 필요에 따라 Microsoft 계정이나 회사 또는 학교 계정으로 로그인할 수 있습니다.

## <a name="tour-of-the-ide"></a>IDE 둘러보기

다음 이미지에서는 Visual Studio에 대한 높은 수준의 시각적 개요를 제공하기 위해 열려 있는 프로젝트가 있는 Visual Studio와 가장 많이 사용하는 몇 가지 주요 도구 창을 보여 줍니다.

![Visual Studio IDE](../ide/media/visualstudioide.png)

- [솔루션 탐색기](../ide/solutions-and-projects-in-visual-studio.md) - 코드 파일을 보고, 탐색하고, 관리할 수 있습니다. 솔루션 탐색기에서 파일을 솔루션 및 프로젝트로 그룹화하여 코드를 구성할 수 있습니다.

- 대부분의 시간을 보낼 가능성이 있는 [편집기](../ide/writing-code-in-the-code-and-text-editor.md) 창은 코드를 보여주고 이를 통해 소스 코드를 편집하고 UI를 디자인할 수 있습니다.

- [출력 창](../ide/reference/output-window.md)에는 디버깅 및 오류 메시지, 컴파일러 경고, 게시 상태 메시지 등의 Visual Studio 알림이 표시됩니다. 각 메시지 원본에 해당하는 탭이 있습니다.

- [팀 탐색기(VSTS)](/vsts/user-guide/work-team-explorer) - [Git](https://git-scm.com/), [TFVC(Team Foundation 버전 제어)](/vsts/tfvc/overview) 등의 버전 제어 기술을 통해 작업 항목을 추적하고 다른 사용자와 코드를 공유할 수 있습니다.

다음은 Visual Studio의 다른 인기 있는 생산성 기능입니다.

- [리팩터링](../ide/refactoring-in-visual-studio.md)에는 변수의 지능형 이름 바꾸기, 선택한 코드 줄을 별도 함수로 이동, 코드를 다른 위치로 이동, 함수 매개 변수 다시 정렬 등의 작업이 포함되어 있습니다.

   ![리팩터링](../ide/media/VSIDE_refactor.png)

- [IntelliSense](../ide/using-intellisense.md) 는 편집기에서 직접 코드에 대한 형식 정보를 표시하고 경우에 따라 약간의 코드를 자동으로 작성하는 인기 있는 기능 집합에 대한 포괄적인 용어입니다. IntelliSense는 별도의 도움말 창에서 형식 정보를 조회할 필요가 없도록 기본 설명서를 편집기에 인라인으로 포함하는 것과 같습니다. IntelliSense 기능은 언어에 따라 달라집니다. 자세한 내용은 [C# IntelliSense](../ide/visual-csharp-intellisense.md), [Visual C++ IntelliSense](../ide/visual-cpp-intellisense.md), [JavaScript IntelliSense](../ide/javascript-intellisense.md) 및 [Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md)를 참조하세요. 다음 그림에서는 일부 IntelliSense 기능의 작동을 보여 줍니다.

   ![Visual Studio 멤버 목록](../ide/media/vs2017_Intellisense.png)

- [빠른 실행](../ide/reference/quick-launch-environment-options-dialog-box.md) 검색 상자는 Visual Studio에서 필요한 항목을 빠르게 찾을 수 있는 좋은 방법입니다. 찾으려는 이름을 입력하기만 하면 Visual Studio는 원하는 곳으로 정확하게 안내하는 결과를 나열합니다. **빠른 실행**은 작업 또는 개별 구성 요소에 대한 **Visual Studio 설치 관리자**를 시작하는 링크도 표시합니다.

   ![빠른 실행 검색 상자](../ide/media/VSIDE_Tour_QuickLaunch.png)

- **오류 표시선**은 물결 모양의 밑줄이며, 입력할 때 코드의 오류 또는 잠재적인 문제를 실시간으로 알려줍니다. 이렇게 하면 컴파일 또는 런타임 중에 오류를 발견할 때까지 기다리지 않고 바로 수정할 수 있습니다. 오류 표시선 위로 마우스를 가져가면 오류에 대한 추가 정보가 표시됩니다. 오류를 수정하기 위한 작업과 함께 전구가 왼쪽 여백에 나타날 수도 있습니다. 자세한 내용은 [빠른 작업](../ide/quick-actions.md)을 참조하세요.

   ![오류 표시선](../ide/media/vs2017_squiggle.png)

- 텍스트 편집기의 상황에 맞는 메뉴에서 [호출 계층 구조](../ide/reference/call-hierarchy.md) 창을 열어 캐럿(삽입 지점) 아래에서 호출하는 메서드와 이 메서드로 호출되는 메서드를 표시할 수 있습니다.

   ![호출 계층 구조 창](../ide/media/VSIDE_call_hierarchy.png)

- [코드 렌즈](../ide/find-code-changes-and-other-history-with-codelens.md)를 사용하면 편집기 내에서 코드 참조, 코드 변경 내용, 연결된 버그, 작업 항목, 코드 검토 및 단위 테스트를 확인할 수 있습니다.

   ![CodeLens](../ide/media/codelensoverview.png)

- [정의 보기](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md) 창은 현재 컨텍스트를 벗어나지 않고 메서드 또는 형식 정의를 인라인으로 표시합니다.

   ![정의 보기](../ide/media/VSIDE_peek_definition.png)

- [정의로 이동](../ide/go-to-and-peek-definition.md) 상황에 맞는 메뉴 옵션은 함수 또는 개체가 정의된 위치로 바로 이동합니다. 편집기에서 마우스 오른쪽 단추를 클릭하면 다른 탐색 명령도 사용할 수 있습니다.

   ![정의로 이동](../ide/media/VSIDE_go_to_definition.png)

## <a name="create-a-program"></a>프로그램 만들기

이제 새롭고 간단한 프로그램을 만들어 보겠습니다.

1. Visual Studio를 엽니다. 메뉴에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

  ![메뉴 모음의 파일 > 새 프로젝트](../ide/media/VSIDE_Tour_NewProject1.png)

1. **새 프로젝트** 대화 상자에는 여러 프로젝트 *템플릿*이 표시됩니다. 템플릿에는 지정된 프로젝트 형식에 필요한 기본 파일과 설정이 포함되어 있습니다. **Visual C#** 에서 **.NET Core** 범주를 선택한 다음 **콘솔 앱(.NET Core)** 템플릿을 선택합니다. **이름** 텍스트 상자에 **HelloWorld**를 입력한 다음, **확인** 단추를 선택합니다.

  ![.NET Core 앱 템플릿](../ide/media/overview-new-project-dialog.png)

   Visual Studio가 프로젝트를 만듭니다. 이 프로젝트는 <xref:System.Console.WriteLine?displayProperty=nameWithType> 메서드를 호출하여 리터럴 문자열 “Hello World!”를 표시하는 간단한 “Hello World” 응용 프로그램입니다. 콘솔 창에 표시합니다.

  > [!NOTE]
  > **.NET Core** 범주가 표시되지 않으면 **.NET Core 플랫폼 간 개발** 워크로드를 설치해야 합니다. 이를 수행하려면 **새 프로젝트** 대화 상자의 왼쪽 아래에 있는 **Visual Studio 설치 관리자 열기** 링크를 선택합니다. **Visual Studio 설치 관리자**가 열리면 아래로 스크롤하여 **.NET Core 플랫폼 간 개발** 워크로드를 선택한 다음, **수정**을 선택합니다.

   잠시 후 다음과 같은 정보가 표시됩니다.

   ![Visual Studio IDE](../ide/media/overview-ide-console-app.png)

   응용 프로그램의 C# 코드는 대부분의 공간을 차지하는 편집기 창에 표시됩니다. 텍스트는 지정된 색으로 자동으로 표시되어 다른 측면(예: 키워드 또는 형식)을 나타냅니다. 또한 코드에서 작은 세로 파선은 서로 일치하는 중괄호를 나타내며, 줄 번호는 나중에 코드를 찾는 데 도움이 됩니다. 작은 상자 안에 있는 빼기 기호를 선택하여 코드를 축소하거나 확장할 수 있습니다. 이 코드 개요 기능을 사용하면 필요 없는 코드를 숨길 수 있으므로 화면 상의 혼란을 최소화할 수 있습니다.

   프로젝트 파일은 **솔루션 탐색기**라는 창의 오른쪽에 나열됩니다.

  ![빨간색 상자가 있는 Visual Studio IDE](../ide/media/overview-ide-console-app-red-boxes.png)

  다른 메뉴와 도구 창을 사용할 수 있지만 지금은 넘어가겠습니다.

1. 이제 앱을 시작합니다. 메뉴 모음의 **디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택하면 됩니다. **Ctrl**+**F5**를 누를 수도 있습니다.

  ![디버그 > 디버깅하지 않고 시작 메뉴](../ide/media/overview-start-without-debugging.png)

  Visual Studio에서 앱을 빌드하며, 콘솔 창이 열리고 **Hello World!** 메시지가 표시됩니다. 이제 실행 중인 앱이 있습니다!

  ![콘솔 창](../ide/media/overview-console-window.png)

1. 콘솔 창을 닫으려면 키보드에서 아무 키나 누릅니다.

1. 앱에 일부 코드를 추가하겠습니다. `Console.WriteLine("Hello World!");` 줄 앞에 다음 C# 코드를 추가합니다.

   ```csharp
   Console.WriteLine("\nWhat is your name?");
   var name = Console.ReadLine();
   ```

   이 코드는 콘솔 창에 **이름이 무엇입니까?** 를 표시한 다음, 사용자가 텍스트를 입력한 후 **Enter** 키를 누를 때까지 기다립니다.

1. `Console.WriteLine("Hello World!");`이라고 표시된 줄을 다음 코드로 변경합니다.

   ```csharp
   Console.WriteLine($"\nHello {name}!");
   ```

1. **디버그** > **디버깅하지 않고 시작**을 선택하거나 **Ctrl**+**F5**를 눌러 앱을 다시 실행합니다.

   Visual Studio에서 앱을 다시 빌드하고, 콘솔 창이 열리며 사용자 이름을 묻는 메시지가 표시됩니다.

1. 콘솔 창에 이름을 입력하고 **Enter** 키를 누릅니다.

   ![콘솔 창 입력](media/overview-console-input.png)

1. 아무 키나 눌러 콘솔 창을 닫고 실행 중인 프로그램을 중지합니다.

## <a name="use-refactoring-and-intellisense"></a>리팩터링 및 IntelliSense 사용

[리팩터링](refactoring-in-visual-studio.md) 및 [IntelliSense](using-intellisense.md)로 더 효율적으로 코딩하는 데 도움이 되는 몇 가지 방법을 살펴보겠습니다.

먼저 `name` 변수의 이름을 변경합니다.

1. `name` 변수를 두 번 클릭하여 선택합니다.

1. 변수의 새 이름 `username`을 입력합니다.

   변수 주위에 회색 상자가 나타나고 여백에 전구가 나타납니다.

1. 전구 아이콘을 선택하여 사용 가능한 [빠른 작업](quick-actions.md)을 표시합니다. **'name'의 이름을 'username'으로 바꾸기**를 선택합니다.

   ![Visual Studio에서 작업 이름 바꾸기](media/rename-quick-action.png)

   프로젝트 전체에서 변수의 이름이 변경됩니다. 이 경우에는 두 군데밖에 없습니다.

   ![Visual Studio에서 이름 바꾸기 리팩터링을 보여 주는 애니메이션된 gif](media/rename-refactoring.gif)

1. 이제 IntelliSense를 살펴보겠습니다. `Console.WriteLine($"\nHello {username}!");`이라고 표시된 줄 아래에 **DateTime now = DateTime**을 입력합니다.

   상자에 <xref:System.DateTime> 클래스의 멤버가 표시됩니다. 또한 현재 선택된 멤버의 설명이 별도 상자에 표시됩니다.

   ![Visual Studio의 IntelliSense 목록 멤버](media/intellisense-list-members.png)

1. 클래스의 속성인 **Now**라는 멤버를 두 번 클릭하거나 **Tab** 키를 눌러 선택합니다. 세미콜론 **;** 를 추가하여 코드 줄을 완료합니다.

1. 그 아래에 다음 코드 줄을 입력하거나 복사합니다.

   ```csharp
   int dayOfYear = now.DayOfYear;

   Console.Write("Day of year: ");
   Console.WriteLine(dayOfYear);
   ```

   > [!TIP]
   > <xref:System.Console.Write%2A?displayProperty=nameWithType>은 인쇄 후 줄 종결자를 추가하지 않는다는 점에서 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>과 약간 다릅니다. 즉, 출력으로 전송되는 다음 텍스트가 같은 줄에 인쇄됩니다. 코드에서 이러한 각 메서드 위로 마우스를 가져가면 설명을 볼 수 있습니다.

1. 다음으로, 리팩터링을 다시 사용하여 코드를 좀 더 간결하게 만듭니다. `DateTime now = DateTime.Now;` 줄에서 변수 `now`를 클릭합니다.

   해당 줄의 여백에 작은 스크루드라이버 아이콘이 나타납니다.

1. 스크루드라이버 아이콘을 클릭하면 Visual Studio에서 제안하는 사항을 볼 수 있습니다. 여기에는 전체 동작을 변경하지 않고 코드 줄을 제거할 수 있는 [인라인 임시 변수](reference/inline-temporary-variable.md) 리팩터링이 표시되어 있습니다.

   ![Visual Studio의 인라인 임시 변수 리팩터링](media/inline-temporary-variable-refactoring.png)

1. **인라인 임시 변수**를 클릭하여 코드를 리팩터링합니다.

1. **Ctrl**+**F5** 키를 눌러 프로그램을 다시 실행합니다. 출력은 다음과 같습니다.

   ![프로그램 출력이 표시된 콘솔 창](../ide/media/overview-console-final.png)

## <a name="debug-code"></a>코드 디버그

코드를 작성할 때 코드를 실행하고 버그를 테스트해야 합니다. Visual Studio의 디버깅 시스템을 사용하면 코드를 단계별로 진행하면서 명령문을 한 번에 하나씩 실행하면서 변수를 검사할 수 있습니다. 지정된 조건이 true인 경우에만 적중되는 중단점을 설정할 수 있습니다. 코드 실행 등과 같은 변수 값을 모니터링할 수 있습니다.

중단점을 설정하여 프로그램이 "이동 중"일 때 `username` 변수의 값을 확인하겠습니다.

1. `Console.WriteLine($"\nHello {username}!");`이라고 표시된 코드 줄을 찾습니다. 이 코드 줄에 중단점을 설정하려면, 즉 이 줄에서 프로그램이 실행을 일시 중지하도록 하려면 편집기의 맨 왼쪽 여백을 클릭합니다. 코드 줄의 아무 곳이나 클릭한 다음, **F9** 키를 누를 수도 있습니다.

   맨 왼쪽 끝에 빨간색 원이 표시되고 코드가 빨간색으로 강조 표시됩니다.

   ![Visual Studio 코드 줄의 중단점](media/breakpoint.png)

1. **디버그** > **디버깅 시작**을 선택하거나 **F5** 키를 눌러 디버깅을 시작합니다.

1. 콘솔 창이 나타나고 사용자 이름을 묻는 메시지가 표시되면 입력하고 **Enter** 키를 누릅니다.

   Visual Studio 코드 편집기로 포커스가 돌아오고 중단점이 있는 코드 줄이 노란색으로 강조 표시됩니다. 이는 프로그램이 실행할 다음 코드 줄을 의미합니다.

1. 마우스를 `username` 변수 위로 가져가면 해당 값을 볼 수 있습니다. 또는 `username`을 마우스 오른쪽 단추로 클릭하고 **조사식 추가**를 선택하여 변수를 **조사식** 창에 추가할 수 있습니다. 이 창에서 해당 값을 볼 수도 있습니다.

   ![Visual Studio에서 디버깅하는 동안 변수 값](media/debugging-variable-value.png)

1. 프로그램 실행을 완료하려면 **F5** 키를 다시 누릅니다.

Visual Studio의 디버깅에 대한 자세한 내용은 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)를 참조하세요.

## <a name="customize-visual-studio"></a>Visual Studio 사용자 지정

기본 색 테마 변경을 포함하여 IDE를 개인 설정할 수 있습니다. **어둡게** 테마로 변경하려면:

1. 메뉴 모음에서 **도구** > **옵션**을 선택하여 **옵션** 대화 상자를 엽니다.

1. **환경** > **일반** 옵션 페이지에서 **색 테마** 선택을 **어두운**으로 변경한 다음, **확인**을 선택합니다.

   전체 IDE의 색 테마가 **어둡게**로 변경됩니다.

   ![어두운 테마의 VS](media/quickstart-personalize-dark-theme.png)

IDE를 개인 설정할 수 있는 다른 방법을 배우려면 [Visual Studio 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

## <a name="learn-more"></a>자세한 정보

Android 또는 iOS 휴대폰용 앱을 만들고 싶으십니까? 3D 게임 또는 클라우드 기반 앱은 어떻습니까? Visual Studio의 이러한 기능 및 기타 기능에 대해 배우려면 [Visual Studio 2017의 기능](../ide/advanced-feature-overview.md)을 참조하세요.

이제 코딩을 시작할 준비가 되었으면 [첫 번째 ASP.NET Core 웹앱 만들기](quickstart-aspnet-core.md)와 같은 목차에서 빠른 시작 항목 중 하나를 선택합니다.

[Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!index=2&lang=1033)에서 제공되는 무료 Visual Studio 과정을 확인할 수도 있습니다.

## <a name="see-also"></a>참고 항목

* [Visual Studio 추가 기능](../ide/advanced-feature-overview.md)
* [www.visualstudio.com](https://www.visualstudio.com/vs/)
* [Visual Studio 블로그](https://blogs.msdn.microsoft.com/visualstudio/)
* [Visual Studio 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)