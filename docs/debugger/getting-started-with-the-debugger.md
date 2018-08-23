---
title: Visual Studio 디버거를 사용 하 여 디버그 하는 방법을 알아봅니다
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 08/01/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 235e9386070d316cd9a4f9751ac1d8f1e8fd92b4
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42623774"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>자습서: Visual Studio를 사용 하 여 디버그 하는 방법을 알아봅니다

이 문서에서는 단계별 연습에서는 Visual Studio 디버거에서의 기능을 소개 합니다. 디버거 기능 상위 수준의 뷰를 원한다 면 참조 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)합니다. 경우 있습니다 *앱을 디버그*, 디버거가 연결 된 응용 프로그램을 실행 하는 일반적으로 의미 합니다. 디버거는 코드 수행 하는 참조 하는 방법은 많습니다 제공 이렇게 하면 실행 중입니다. 시계를 설정할 수 있습니다에 코드를 단계별로 실행 하 고 변수에 저장 된 값을 살펴보고 값이 변경 될 때를 확인 하려면 변수를 코드의 실행 경로 검사, 코드 분기의 실행 등 인지 수 있습니다. 읽을 하려는 처음 코드를 디버그 하려는 경우 [초보자를 위한 디버깅](../debugger/debugging-absolute-beginners.md) 이 문서를 진행 하기 전에 합니다.

|         |         |
|---------|---------|
|  ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기")  |    [비디오를 시청](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171) 비슷한 단계를 보여 주는 디버깅 합니다. |

데모 앱을 C# 및 c + + 있지만 기능은 Visual Basic, JavaScript 및 Visual Studio (언급 한 위치 제외) 지 원하는 다른 언어에 적용할 수 있습니다. 스크린샷은 C#의 경우 C# 및 c + + 샘플 코드 사이 전환 하려면 페이지의 오른쪽 위에 있는 언어 필터를 사용 합니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 디버거를 시작 하 고 중단점을 적중 합니다.
> * 디버거에서 코드를에서 단계별로 실행 하려면 명령에 알아보기
> * 데이터 팁 및 디버거 창에서 변수 검사
> * 호출 스택을 검사합니다

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017이 설치 되어 있어야 하며 **.NET 데스크톱 개발** 하거나 **c + +를 사용한 데스크톱 개발** 워크 로드.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

    워크로드를 설치해야 하지만 이미 Visual Studio가 있는 경우 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다(**파일** > **새로 만들기** > **프로젝트**를 선택합니다). Visual Studio 설치 관리자가 시작됩니다. 선택 합니다. **NET 데스크톱 개발** 하거나 **c + +를 사용한 데스크톱 개발** 워크 로드를 선택한 **수정**합니다.

## <a name="create-a-project"></a>프로젝트 만들기

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택합니다.

2. 아래 **Visual C#** 또는 **Visual c + +**, 선택 **Windows Desktop**를 선택한 다음 가운데 창에서 **콘솔 앱** ( **Windows 콘솔 응용 프로그램** c + +에서).

    표시 되지 않는 경우는 **콘솔 응용 프로그램** 템플릿 프로젝트를 클릭 합니다 **Visual Studio 설치 관리자 열기** 링크의 왼쪽된 창에서를 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자가 시작됩니다. 선택 된 *.NET 데스크톱 개발** 또는 **c + +를 사용한 데스크톱 개발** 워크 로드를 선택한 **수정**합니다.

3. 같은 이름을 입력 **get-시작-디버깅** 누릅니다 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

4. *Program.cs* (C#) 또는 *get 시작 debugging.cpp* (c + +), 다음 코드를 대체 합니다.

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;

    namespace get_started_debugging
    {
        class Program
        {
            static void Main(string[] args)
            {
            }
        }
    }
    ```

    ```c++
    int main()
    {
        return 0;
    }
    ```

    이 코드로 바꿉니다.

    ```csharp
    using System;
    using System.Collections.Generic;

    public class Shape
    {
        // A few example members
        public int X { get; private set; }
        public int Y { get; private set; }
        public int Height { get; set; }
        public int Width { get; set; }
   
        // Virtual method
        public virtual void Draw()
        {
            Console.WriteLine("Performing base class drawing tasks");
        }
    }

    class Circle : Shape
    {
        public override void Draw()
        {
            // Code to draw a circle...
            Console.WriteLine("Drawing a circle");
            base.Draw();
        }
    }

    class Rectangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a rectangle...
            Console.WriteLine("Drawing a rectangle");
            base.Draw();
        }
    }

    class Triangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a triangle...
            Console.WriteLine("Drawing a trangle");
            base.Draw();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {

            var shapes = new List<Shape>
            {
                new Rectangle(),
                new Triangle(),
                new Circle()
            };

            foreach (var shape in shapes)
            {
                shape.Draw();
            }

            // Keep the console open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }

    }

    /* Output:
        Drawing a rectangle
        Performing base class drawing tasks
        Drawing a triangle
        Performing base class drawing tasks
        Drawing a circle
        Performing base class drawing tasks
    */
    ```

    ```c++
    #include "pch.h"

    #include <string>
    #include <vector>
    #include <iostream>

    class Shape
    {
        int privateX = 0;
        int privateY = 0;
        int privateHeight = 0;
        int privateWidth = 0;

        int getX() const { return privateX; }
        void setX(int value) { privateX = value; }

        int getY() const { return privateY; }
        void setY(int value) { privateY = value; }

        int getHeight() const { return privateHeight; }
        void setHeight(int value) { privateHeight = value; }

        int getWidth() const { return privateWidth; }
        void setWidth(int value) { privateWidth = value; }

        public:
        // Virtual method
        virtual void Draw()
        {
            std::wcout << L"Performing base class drawing tasks" << std::endl;
        }
    };

    class Circle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a circle...
        std::wcout << L"Drawing a circle" << std::endl;
        Shape::Draw();
        }
    };

    class Rectangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a rectangle...
        std::wcout << L"Drawing a rectangle" << std::endl;
        Shape::Draw();
        }
    };

    class Triangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a triangle...
        std::wcout << L"Drawing a trangle" << std::endl;
        Shape::Draw();
        }
    };

    int main(std::vector<std::wstring> &args)
    {
        auto shapes = std::vector<Shape*>
        {
            new Rectangle(),
            new Triangle(),
            new Circle()
        };

        for (auto shape : shapes)
        {
            shape->Draw();
        }
    }

    /* Output:
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    */
    ```

## <a name="start-the-debugger"></a>디버거를 시작 합니다!

1. 키를 눌러 **F5** (**디버그 > 디버깅 시작**) 또는 **디버깅 시작** 단추 ![디버깅 시작](../debugger/media/dbg-tour-start-debugging.png "디버깅 시작 ") 디버그 도구 모음에서 합니다.

     **F5** 디버거를 사용 하 여 앱을 앱에 연결 하는 시작을 처리 하지만 지금 코드를 검사 하기 위해 특별히 수행 하지 않은 것입니다. 응용 프로그램이 방금 로드 되므로 및 콘솔 출력을 표시 합니다.

    ```
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    ```

     이 자습서에서는 디버거를 사용 하 여이 앱에 자세히 살펴보겠습니다 하 고 살펴보세요 디버거 기능.

2. 빨간색 중지 키를 눌러 디버거를 중지 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 단추입니다.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점을 설정 하 고 디버거를 시작

1. 에 `foreach` 의 루프를 `Main` 함수 (`for` c + +에서 루프 `main` 함수), 코드의 첫 번째 줄의 왼쪽된 여백을 클릭 하 여 중단점을 설정 합니다.

    ![중단점을 설정](../debugger/media/get-started-set-breakpoint.png "SetABreakPoint")

    빨간색 원이 나타납니다 중단점을 설정 합니다.

    중단점은 신뢰할 수 있는 디버깅의 가장 기본적이 고 필수적인 기능입니다. 중단점은 변수의 값, 메모리의 동작 또는 코드 분기의 실행 여부를 확인할 수 있도록 Visual Studio에서 실행 중인 코드를 일시 중단해야 하는 위치를 나타냅니다. 

6. 키를 눌러 **F5** 또는 **디버깅 시작** 앱 시작 단추 및 디버거에서 중단점을 설정한 코드 줄을 실행 합니다.

    ![중단점을 적중](../debugger/media/get-started-hit-breakpoint.png "HitABreakPoint")

    노란색 화살표는도 동일한 지점 (이 문에 아직 실행)에서 앱 실행을 일시 중단 되는 디버거가 일시 중지, 문을 나타냅니다.

     앱을 아직 실행 하지 않는 경우 **F5** 디버거를 시작 하 고 첫 번째 중단점에서 중지 합니다. 그렇지 않으면 **F5** 계속 다음 중단점까지 앱을 실행 합니다.

    중단점은 코드의 줄 또는 자세히 검사 하려는 코드 부분을 알고 있는 경우는 유용한 기능입니다.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>단계 명령을 사용 하 여 디버거에서 코드를 이동 합니다.

주로 사용 하 여 바로 가기 키를 여기에서 얻을 수는 좋은 방법 이기 때문에 (해당 하는 등의 명령 메뉴 명령을 괄호 안에 표시 됩니다) 디버거에서 앱 실행 시 빠른 합니다.

1. 키를 누릅니다 **F11** (선택 하거나 **디버그 > 한 단계씩 코드 실행**) (여러 번에 C#) 두 번에서 일시 중지 될 때까지 `shape.Draw` 메서드 호출을 `Main` 메서드 (`shape->Draw` c + +에서).

1. 키를 눌러 **F11** 에 대 한 코드로 이동 하는 한 번 더는 `Rectangle` 클래스입니다.

     ![F11 키를 한 단계씩 코드 실행 코드 사용](../debugger/media/get-started-f11.png "F11 한 단계씩 코드 실행")

     F11은는 **한 단계씩 코드 실행** 명령 및 한 번에 앱 실행 하나의 문 앞으로 이동 합니다. F11이 대부분의 정보에 실행 흐름을 검사 하는 것이 좋습니다. (이동할 더 빠르게 코드를 통해 살펴보겠습니다 몇 가지 다른 옵션 또한.) 기본적으로 디버거를 건너뜁니다 사용자 코드가 아닌 (자세한 정보를 원하는 경우 참조 [Just My Code](../debugger/just-my-code.md)).

2. 키를 누릅니다 **F10** (선택 또는 **디버그 > 프로시저 단위 실행**)를 몇 번까지에서 디버거를 중지 합니다 `base.Draw` 메서드 호출 (`Shape::Draw` c + +에서)를 누릅니다 **F10** 또 한 번.

     ![F10 프로시저 단위 실행 코드를 사용 하 여](../debugger/media/get-started-step-over.png "F10 프로시저 단위 실행")

     디버거에서 한 단계씩 실행 하지 않습니다는이 이번 공지 합니다 `Draw` 기본 클래스의 메서드 (`Shape`). **F10** 함수나 (코드가 계속 실행) 앱 코드에서 메서드를 한 단계씩 실행 하지 않고 디버거를 이동 합니다. F10 키를 눌러 합니다 `base.Draw` (또는 `Shape::Draw`) 메서드 호출 (대신 **F11**)를 구현 코드에 대해 생략 했습니다 `base.Draw` (우리는 관심이 지금는 maybe).

## <a name="navigate-code-using-run-to-click"></a>실행 하려면 클릭을 사용 하 여 코드 탐색

5. 코드 편집기에서 아래로 스크롤하여 마우스로 합니다 `Console.WriteLine` 메서드 (`std::cout` c + +에서)에 `Triangle` 녹색까지 클래스 **실행 하려면 클릭** 단추 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png " RunToClick") 왼쪽에 표시 됩니다.

     ![실행 하려면 클릭을 사용 하 여 기능](../debugger/media/get-started-run-to-click.png "실행 하려면 클릭")

    >  [!NOTE]
    > 합니다 **실행 하려면 클릭** 단추에서 새로운 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다. 찾을 수 없으면 녹색 화살표 단추를 사용 하 여 **F11** 이 예제의 대신 디버거가 올바른 위치로 이동 합니다.

6. 클릭 합니다 **실행 하려면 클릭** 단추 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick")합니다.

    이 단추를 사용 하는 것은 임시 중단점을 설정 하는 것과 비슷합니다. **실행 하려면 클릭** (열려 있는 특정 파일에서 클릭 수)는 앱 코드의 표시 영역 내에서 신속 하 게 살펴보기에 유용 합니다.

    디버거를 이동 합니다 `Console.WriteLine` 메서드 구현에 대 한 합니다 `Triangle` 클래스 (`std::cout` c + +에서).

    일시 중지 하는 동안 오타를 확인할 수 있습니다. "는 trangle 그리기" 출력 맞춤법이 잘못 되었습니다. 바로 여기 디버거에서 앱을 실행 하는 동안 수정할 수 있습니다.

## <a name="edit-code-and-continue-debugging"></a>코드를 편집하며 디버그 계속하기

1. 클릭 "을 trangle 그리기" 및 "triangle" 변경 "trangle" 수정 사항을 입력 합니다.

1. 키를 눌러 **F11** 한 번 표시 디버거를 다시 이동 합니다.

    > [!NOTE]
    > 디버거에서 편집 어떤 유형의 코드에 따라 경고 메시지가 표시 될 수 있습니다. 일부 시나리오에서는 코드를 계속 하기 전에 다시 컴파일해야 할 수 있습니다.

## <a name="step-out"></a>프로시저 나가기

완료 되는 경우를 가정해 검사는 `Draw` 의 메서드는 `Triangle` 클래스 하려는 함수의 가져오지만 디버거에서 유지 합니다. 사용 하 여 수행할 수 있습니다 합니다 **프로시저 나가기** 명령입니다.

1. 키를 눌러 **Shift** + **F11** (또는 **디버그 > 프로시저 나가기**).

     앱 실행을 다시 시작 (및 디버거 이동)이이 명령은 현재 함수가 반환 될 때까지 합니다.

     다시 해야 합니다 `foreach` 루프를 `Main` 메서드 (`for` 루프에서 c + +).

## <a name="restart-your-app-quickly"></a>앱을 신속 하 게 다시 시작

클릭 합니다 **다시 시작** ![앱 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 디버그 도구 모음에서 단추 (**Ctrl** + **Shift**   +  **F5**).

누르면 **다시 시작**, 앱을 중지 하 고 디버거를 다시 시작 및 시간을 절약 합니다. 코드를 실행 하 여 적중 되는 첫 번째 중단점에서 디버거가 일시 중지 합니다.

에 설정한 중단점에서 디버거를 다시 중지 합니다 `foreach` 루프 (`for` 루프에서 c + +).

## <a name="inspect-variables-with-data-tips"></a>데이터 팁을 사용 하 여 변수를 검사 합니다.

변수를 검사할 수 있도록 하는 기능은 디버거에서의 가장 유용한 기능 중 하나 및 작업을 수행 하는 방법은 여러 가지입니다. 종종 문제를 디버깅 하려고 할 때 변수 값으로 특정 시간에 예상 되는 저장 하는 여부를 확인 하려고 합니다.

1. 일시 중지 된 동안 합니다 `foreach` 루프 (`for` 루프에서 c + +), 키를 누릅니다 **F11** 되 면 합니다.

1. 마우스로 합니다 `shapes` 개체의 기본 속성 값, 참조는 `Count` 속성.

1. 확장을 `shapes` 개체 배열의 첫 번째 인덱스 등의 모든 해당 속성을 보려는 `[0]`의 값 `Rectangle` (C#) 또는 메모리 주소 (c + +).

     ![데이터 팁을 보려면](../debugger/media/get-started-data-tip.png "데이터 팁 보기")

    종종를 디버깅할 때 개체에 대 한 속성 값을 확인 하는 빠른 방법 및 데이터 팁은 작업을 수행 하는 좋은 방법입니다.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>자동 및 지역 창을 사용 하 여 변수를 검사 합니다.

1. 확인 합니다 **자동** 코드 편집기의 맨 아래에 있는 창입니다.

     ![자동 창에서 변수를 검사할](../debugger/media/get-started-autos-window.png "자동 창")

    에 **자동** 창 변수와 해당 현재 값을 표시 합니다. 합니다 **자동** 창에 현재 줄 이나 이전 줄에 사용 되는 모든 변수 표시 (c + +, 창에는 표시 변수 이전 세 줄의 코드만으로 합니다. 언어별 동작에 대 한 설명서를 참조).

    > [!NOTE]
    > JavaScript에는 **지역** 창이 아닌 지원 되는 **자동** 창.

2. 다음을 확인 하는 **지역** 창에서 다음을 탭 합니다 **자동** 창.

    합니다 **지역** 창에 현재 있는 변수를 보여 줍니다. [범위](https://www.wikipedia.org/wiki/Scope_(computer_science))합니다.

## <a name="set-a-watch"></a>조사식 설정

1. 기본 코드 편집기 창에서 마우스 오른쪽 단추로 클릭 합니다 `shapes` 선택한 개체 **조사식 추가**합니다.

    합니다 **조사식** 코드 편집기의 맨 아래에 있는 창이 열립니다. 사용할 수는 **조사식** 창에서 변수 (또는 식을) 주시 하려는 지정 합니다.

    이제 설정 조사식은 `shapes` 개체, 디버거를 통해 이동할 때 변경 해당 값을 볼 수 있습니다. 다른 변수 창과 달리 합니다 **조사식** 창 항상 표시 변수 조사 중인 (해당 하는 회색으로 표시 될 때 범위를 벗어납니다).

## <a name="examine-the-call-stack"></a>호출 스택을 검사합니다

1. 일시 중지 된 동안는 `foreach` 루프 (`for` 루프에서 c + +)를 클릭 합니다 **호출 스택** 기본적으로 오른쪽 아래 창에 열려 있는 창을.

1. 클릭 **F11** 를 여러 번 표시 될 때까지 디버거가 일시 중지 된 `Circle.Draw` 메서드 코드 편집기에서. 확인 합니다 **호출 스택** 창입니다.

    ![호출 스택을 검사할](../debugger/media/get-started-call-stack.png "ExamineCallStack")

    합니다 **호출 스택** 창 있는 메서드 및 함수는 호출 되는 순서를 보여 줍니다. 맨 위 줄 현재 함수를 보여 줍니다 (합니다 `Circle.Draw` 또는 `Circle::Draw` 이 앱에서 메서드). 두 번째 줄을 보여 줍니다 `Circle.Draw` 에서 호출한 합니다 `Main` 메서드 (`main` c + +에서) 등입니다.

    >  [!NOTE]
    > 합니다 **호출 스택** Eclipse와 같은 일부 Ide 창에 디버그 관점 비슷합니다.

    호출 스택은 좋은 점검 하 여 앱의 실행 흐름을 이해 합니다.

    해당 소스 코드를 살펴볼 코드 줄을 두 번 클릭 수 및 디버거에 의해 검사 되 고 현재 범위를 변경 하는 합니다. 이 그러면 디버거를 진행 하지 않습니다.

    오른쪽 클릭 메뉴에서 사용할 수도 있습니다는 **호출 스택** 다른 작업을 수행 하는 창입니다. 예를 들어, 있습니다 지정 된 함수에 중단점을 삽입을 사용 하 여 디버거를 계속 진행 **커서까지 실행**, 이동한 소스 코드를 검사 합니다. 자세한 내용은 [방법: 호출 스택 검사](../debugger/how-to-use-the-call-stack-window.md)합니다.

## <a name="change-the-execution-flow"></a>실행 흐름 변경

1. 디버거가 일시 중지 된 상태에서 합니다 `Circle.Draw` 메서드 호출, 키를 누릅니다 **F11** 몇 시간이 될 때까지 디버거가 일시 중지 합니다 `base.Draw` 메서드 호출 (`Shape::Draw` c + +에서).

1. 마우스를 사용 하 여 왼쪽의 노란색 화살표 (실행 포인터)를 선택 하 고 노란색 화살표를 한 줄 위로 이동 하는 `Console.WriteLine` (`std::cout` c + +에서) 메서드를 호출 합니다.

1. 키를 눌러 **F11** 한 번 더 합니다.

    디버거를 다시 실행 합니다 `Console.WriteLine` 메서드 (`std::cout` c + +에서).

    실행 흐름을 변경 하면 다른 코드 실행 경로 테스트 하거나 디버거를 다시 시작 하지 않고 코드를 다시 실행 하는 등 작업을 수행할 수 있습니다.

    > [!WARNING]
    > 이 기능을 사용 하 여 주의 해야 하는 경우가 많습니다 및 도구 설명에 경고를 표시 합니다. 다른 경고를 너무 표시 될 수 있습니다. 포인터를 이동 하면 응용 프로그램을 이전 앱 상태를 되돌릴 수 없습니다.

1. 키를 눌러 **F5** 계속 앱을 실행 합니다.

    축하합니다. 이 자습서를 마쳤습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 디버거를 시작 하면 코드를 단계별로 실행 하 여 변수를 검사 하는 방법을 알아보았습니다. 자세한 정보에 대 한 링크와 함께 디버거 기능에 간략히 살펴보고 가져오려는 수 있습니다.

> [!div class="nextstepaction"]
> [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)
