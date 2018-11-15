---
title: Visual Studio 디버거를 통한 디버깅 학습
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: debug-experiment
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
ms.openlocfilehash: d832753b798cc9e476b675f8791c1ab245b3adee
ms.sourcegitcommit: a34b7d4fdb3872865fcf98ba24a0fced58532adc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51561675"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>자습서: Visual Studio를 통한 디버깅 학습

이 문서에서는 단계별 연습을 통해 Visual Studio 디버거의 기능을 소개합니다. 디버거 기능을 개략적으로 살펴보려면 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)를 참조하세요. *애플리케이션을 디버그*하는 경우는 일반적으로 디버거가 연결된 상태에서 애플리케이션을 실행하고 있음을 의미합니다. 이렇게 하면 디버거가 실행되는 동안 코드에서 수행하는 작업을 확인할 수 있는 여러 가지 방법이 제공됩니다. 코드를 단계별로 실행하고, 변수에 저장된 값을 살펴보고, 변수에 대한 조사식을 설정하여 값이 변경되는 경우를 확인하며, 코드의 실행 경로를 검사하고, 코드의 분기가 실행되는지 등을 확인할 수 있습니다. 코드를 처음으로 디버그하려고 하는 경우 이 문서를 계속 진행하기 전에 먼저 [완전 초보자를 위한 디버깅](../debugger/debugging-absolute-beginners.md)을 참조하는 것이 좋습니다.

| | |
|---------|---------|
| ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기") | 비슷한 단계를 보여 주는 [디버깅에 대한 비디오를 시청하세요](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171). |

데모 애플리케이션은 C# 및 C++이지만, 기능은 Visual Basic, JavaScript 및 Visual Studio에서 지원하는 다른 언어(언급한 경우 제외)에 적용할 수 있습니다. 스크린샷은 C#에 있습니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 디버거 시작 및 중단점 적중
> * 디버거에서 코드를 단계별로 실행하는 명령 학습
> * 데이터 팁 및 디버거 창에서 변수 검사
> * 호출 스택 검사

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2017이 설치되어 있고, **.NET 데스크톱 개발** 또는 **C++를 사용한 데스크톱 개발** 워크로드가 있어야 합니다.

    아직 Visual Studio를 설치하지 않은 경우  [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)  페이지로 이동하여 체험용으로 설치합니다.

    워크로드를 설치해야 하지만 이미 Visual Studio가 있는 경우 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다(**파일** > **새로 만들기** > **프로젝트**를 선택합니다). Visual Studio 설치 관리자가 시작됩니다. **NET 데스크톱 개발** 또는 **C++를 사용한 데스크톱 개발** 워크로드를 선택한 다음, **수정**을 선택합니다.

## <a name="create-a-project"></a>프로젝트 만들기

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택합니다.

2. **Visual C#** 또는 **Visual C++** 아래에서 **Windows 데스크톱**을 선택한 다음, 가운데 창에서 **콘솔 애플리케이션**(C++의 경우 **Windows 콘솔 애플리케이션**)을 선택합니다.

    **콘솔 애플리케이션** 프로젝트 템플릿이 표시되지 않으면 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Studio 설치 관리자 열기** 링크를 클릭합니다. Visual Studio 설치 관리자가 시작됩니다. *.NET 데스크톱 개발** 또는 **C++를 사용한 데스크톱 개발** 워크로드를 선택한 다음, **수정**을 선택합니다.

3. **get-started-debugging**과 같은 이름을 입력하고 **확인**을 클릭합니다.

    Visual Studio가 프로젝트를 만듭니다.

    > [!NOTE]
    > 이 문서에서 C# 및 C++ 샘플 코드 간에 전환하려면 이 페이지 오른쪽 위에 있는 언어 필터를 사용하세요.

4. *Program.cs* (C#) 또는 *get-started-debugging.cpp*(C++)에서 다음 코드를

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

## <a name="start-the-debugger"></a>디버거 시작!

1. **F5** 키(**디버그 > 디버깅 시작**) 또는 **디버깅 시작** 단추 ![디버깅 시작](../debugger/media/dbg-tour-start-debugging.png "디버깅 시작")를 누릅니다.

     **F5** 키는 애플리케이션 프로세스에 디버거가 연결된 상태에서 애플리케이션을 시작하지만, 지금은 코드를 검사하기 위한 특별한 작업을 수행하지 않았습니다. 따라서 애플리케이션이 로드되고 콘솔 출력이 표시됩니다.

    ```
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    ```

     이 자습서에서는 디버거를 사용하여 이 애플리케이션을 자세히 살펴보고 디버거 기능도 살펴봅니다.

2. 빨간색 중지 ![디버깅 중지](../debugger/media/dbg-tour-stop-debugging.png "디버깅 중지") 단추를 눌러 디버거를 중지합니다.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점 설정 및 디버거 시작

1. `Main` 함수의 `foreach` 루프(`main` C++ 함수의 경우 `for` 루프)에서 다음 코드 줄의 왼쪽 여백을 클릭하여 중단점을 설정합니다.

    `shape.Draw()`(또는 C++의 경우 `shape->Draw()`)

    중단점을 설정하면 빨간색 원이 나타납니다.

    중단점은 신뢰할 수 있는 디버깅의 가장 기본적이 고 필수적인 기능입니다. 중단점은 변수의 값, 메모리의 동작 또는 코드 분기의 실행 여부를 확인할 수 있도록 Visual Studio에서 실행 중인 코드를 일시 중단해야 하는 위치를 나타냅니다. 

6. **F5** 키 또는 **디버깅 시작** 단추를 누릅니다. 그러면 애플리케이션이 시작되고, 중단점이 설정된 코드 줄에서 디버거가 실행됩니다.

    ![중단점 설정 및 적중](../debugger/media/get-started-set-breakpoint.gif)

    노란색 화살표는 디버거가 일시 중지한 명령문을 나타내며, 동일한 지점에서 애플리케이션 실행을 일시 중단하기도 합니다(이 명령문은 아직 실행되지 않았음).

     애플리케이션이 아직 실행되고 있지 않으면 **F5** 키를 사용하여 디버거를 시작하고 첫 번째 중단점에서 중지합니다. 그렇지 않으면 **F5** 키를 사용하여 다음 중단점까지 애플리케이션을 계속 실행합니다.

    중단점은 자세히 검사하려는 코드 줄 또는 코드 섹션을 확인할 때 유용한 기능입니다.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>한 단계 실행 명령을 사용하여 디버거에서 코드 탐색

대부분의 경우 바로 가기 키를 사용합니다. 바로 가기 키는 디버거에서 애플리케이션을 빠르게 실행할 수 있는 좋은 방법입니다(메뉴 명령과 같이 동등한 명령이 괄호 안에 표시되어 있음).

1. `Main` 메서드의 `shape.Draw` 메서드(C++의 경우 `shape->Draw`) 호출에서 일시 중지한 상태에서 **F11** 키를 눌러(또는 **디버그 > 한 단계씩 코드 실행** 선택) `Rectangle` 클래스에 대한 코드로 이동합니다.

     ![F11 키를 사용하여 한 단계씩 코드 실행](../debugger/media/get-started-f11.png "F11 한 단계씩 코드 실행")

     F11 키는 **한 단계씩 코드 실행** 명령이고 한 번에 하나의 명령문을 실행합니다. F11 키는 실행 흐름을 가장 자세히 검사할 수 있는 좋은 방법입니다. (코드에서 더 빨리 이동할 수 있도록 몇 가지 다른 옵션도 표시합니다.) 기본적으로 디버거는 비사용자 코드가 아닌 코드를 건너뜁니다. 자세한 내용은 [내 코드만](../debugger/just-my-code.md)을 참조하세요.

2. 디버거가 `base.Draw` 메서드(C++의 경우 `Shape::Draw`) 호출에서 중지할 때까지 **F10** 키를 몇 번 누른(또는 **디버그 > 프로시저 단위 실행** 선택) 다음, **F10** 키를 한 번 더 누릅니다.

     ![F10 키를 사용하여 프로시저 단위 코드 실행](../debugger/media/get-started-step-over.png "F10 프로시저 단위 실행")

     지금은 디버거에서 기본 클래스(`Shape`)의 `Draw` 메서드를 한 단계씩 실행하지 않습니다. **F10** 키는 애플리케이션 코드의 함수 또는 메서드를 한 단계씩 실행하지 않고 디버거를 진행합니다(코드는 계속 실행되고 있음). `base.Draw`(또는 `Shape::Draw`) 메서드 호출에서 F10 키(**F11** 키 대신)를 눌러 `base.Draw`에 대한 구현 코드(지금은 관심이 없을 수 있음)를 건너뛰었습니다.

## <a name="navigate-code-using-run-to-click"></a>실행하려면 클릭을 사용하여 코드 탐색

5. 코드 편집기에서 **실행하려면 클릭** 녹색 단추 ![실행하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick")이 왼쪽에 나타날 때까지 `Triangle` 클래스의 `Console.WriteLine` 메서드(C++의 경우 `std::cout`)를 아래로 스크롤하여 마우스로 가리킵니다.

     ![실행하려면 클릭 기능 사용](../debugger/media/get-started-run-to-click.png "실행하려면 클릭")

   > [!NOTE]
   > **실행하려면 클릭** 단추는 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]의 새로운 기능입니다. 녹색 화살표 단추가 표시되지 않으면 이 예에서 **F11** 키를 대신 사용하여 디버거를 올바른 위치로 이동시킵니다.

6. **실행하려면 클릭** 단추 ![실행하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick")을 클릭합니다.

    이 단추를 사용하는 것은 임시 중단점을 설정하는 것과 비슷합니다. **실행하려면 클릭**은 애플리케이션 코드의 표시 영역 내에서 빠르게 이동할 수 있습니다(열려 있는 파일은 모두 클릭할 수 있음).

    디버거에서 `Triangle` 클래스에 대한 `Console.WriteLine` 메서드(C++의 경우 `std::cout`) 구현으로 이동합니다.

    일시 중지한 상태에서 오타가 있음을 알 수 있습니다! "Drawing a trangle" 출력의 철자가 틀립니다. 디버거에서 애플리케이션을 실행하면서 바로 여기에서 수정할 수 있습니다.

## <a name="edit-code-and-continue-debugging"></a>코드를 편집하며 디버그 계속하기

1. "Drawing a trangle"을 클릭하고 "trangle"을 "triangle"로 수정합니다.

1. **F11** 키를 한 번 누르면 디버거가 다시 진행됩니다.

    > [!NOTE]
    > 디버거에서 편집하는 코드 형식에 따라 경고 메시지가 표시될 수 있습니다. 일부 시나리오에서는 코드를 다시 컴파일해야 계속 진행할 수 있습니다.

## <a name="step-out"></a>프로시저 나가기

`Triangle` 클래스의 `Draw` 메서드를 검사했고 함수에서 나가려고 하지만 디버거에 남아 있다고 가정해 보겠습니다. 이 작업은 **프로시저 나가기** 명령을 사용하여 수행할 수 있습니다.

1. **Shift** + **F11** 키(또는 **디버그 > 프로시저 나가기**)를 누릅니다.

     이 명령은 현재 함수가 반환될 때까지 애플리케이션 실행을 다시 시작하고 디버거를 진행시킵니다.

     `Main` 메서드의 `foreach` 루프(C++의 경우 `for` 루프)로 돌아와야 합니다.

## <a name="restart-your-app-quickly"></a>애플리케이션을 빠르게 다시 시작

디버그 도구 모음에서 **다시 시작** ![애플리케이션 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 단추를 클릭합니다(**Ctrl** + **Shift** + **F5**).

**다시 시작**을 누르면 애플리케이션을 중지하고 디버거를 다시 시작하는 것보다 더 많은 시간이 절약됩니다. 디버거가 코드를 실행하여 적중한 첫 번째 중단점에서 일시 중지합니다.

디버거가 `shape.Draw()` 메서드(C++의 경우 `shape->Draw()`)에서 설정한 중단점에서 다시 중지합니다.

## <a name="inspect-variables-with-data-tips"></a>데이터 팁을 사용하여 변수 검사

변수를 검사할 수 있는 기능은 디버거의 가장 유용한 기능 중 하나이며, 이를 수행하는 다양한 방법이 있습니다. 문제를 디버그하려고 할 때 변수에서 특정 시간에 제공하도록 예상되는 값을 저장하고 있는지 여부를 확인하려고 하는 경우가 많습니다.

1. `shape.Draw()` 메서드(C++의 경우 `shape->Draw()`)에서 일시 중지한 상태에서 마우스로 `shapes` 개체 위를 가리키면 해당 기본 속성 값인 `Count` 속성이 표시됩니다.

1. `shapes` 개체를 확장하여 값이 `Rectangle`(C#)이거나 메모리 주소(C++)인 `[0]` 배열의 첫 번째 인덱스와 같은 모든 속성을 표시합니다.

     ![데이터 팁 보기](../debugger/media/get-started-data-tip.gif "데이터 팁 보기")

    개체를 추가로 확장하여 사각형의 `Height` 속성과 같은 속성을 표시할 수 있습니다.

    디버그할 때 개체의 속성 값을 빠르게 확인할 수 있는 방법을 원하는 경우가 많으며 데이터 팁은 이 작업을 수행할 수 있는 좋은 방법입니다.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>자동 및 지역 창을 사용하여 변수 검사

1. 코드 편집기의 아래쪽에 있는 **자동** 창을 살펴봅니다.

     ![자동 창에서 변수 검사](../debugger/media/get-started-autos-window.png "자동 창")

    **자동** 창에는 변수와 해당 현재 값이 표시됩니다. **자동** 창에서는 현재 줄 또는 이전 줄에 사용된 모든 변수를 표시합니다(C++의 창에서는 이전 세 개의 코드 줄에 있는 변수를 표시합니다. 언어별 동작에 대한 설명서를 참조하세요).

    > [!NOTE]
    > JavaScript에는 **지역** 창이 지원되지만 **자동** 창은 지원되지 않습니다.

2. 그런 다음, **자동** 창 옆의 탭에 있는 **지역** 창을 살펴봅니다.

    **지역** 창에는 현재 [범위](https://www.wikipedia.org/wiki/Scope_(computer_science))에 있는 변수가 표시됩니다.

## <a name="set-a-watch"></a>조사식 설정

1. 기본 코드 편집기 창에서 `shapes` 개체를 마우스 오른쪽 단추로 클릭하고 **조사식 추가**를 선택합니다.

    코드 편집기의 아래쪽에서 **조사식** 창이 열립니다. **조사식** 창을 사용하여 주시하려는 변수(또는 식)를 지정할 수 있습니다.

    이제 `shapes` 개체에 설정된 조사식이 있으며, 디버거에서 이동하면서 해당 값의 변화를 확인할 수 있습니다. 다른 변수 창과 달리 **조사식** 창에는 항상 주시하고 있는 변수가 표시됩니다(범위를 벗어나면 회색으로 표시됨).

## <a name="examine-the-call-stack"></a>호출 스택 검사

1. `foreach` 루프(C++의 경우 `for` 루프)에서 일시 중지한 상태에서 **호출 스택** 창을 클릭합니다. 이 창은 기본적으로 오른쪽 아래의 창에서 열립니다.

2. 코드 편집기의 `Circle.Draw` 메서드에서 디버거가 일시 중지할 때까지 **F11** 키를 몇 번 클릭합니다. **호출 스택** 창을 살펴봅니다.

    ![호출 스택 검사](../debugger/media/get-started-call-stack.png "ExamineCallStack")

    **호출 스택** 창에는 메서드와 함수가 호출되는 순서가 표시됩니다. 맨 위쪽의 줄에는 현재 함수(이 애플리케이션의 `Circle.Draw` 또는 `Circle::Draw` 메서드)가 표시됩니다. 두 번째 줄에는 `Main` 메서드(C++의 `main`)에서 `Circle.Draw`가 호출되었음이 표시됩니다.

   > [!NOTE]
   > **호출 스택** 창은 Eclipse와 같은 일부 IDE의 디버그 관점과 비슷합니다.

    호출 스택은 애플리케이션의 실행 흐름을 검사하고 파악할 수 있는 좋은 방법입니다.

    코드 줄을 두 번 클릭하여 해당 소스 코드를 살펴보고, 디버거에서 검사하고 있는 현재 범위를 변경할 수도 있습니다. 이 작업은 디버거를 진행시키지 않습니다.

    또한 **호출 스택** 창에서 오른쪽 클릭 메뉴를 사용하여 다른 작업을 수행할 수도 있습니다. 예를 들어 지정된 함수에 중단점을 삽입하고, **커서까지 실행**을 사용하여 디버거를 진행시키고, 소스 코드를 검사할 수 있습니다. 자세한 내용은 [방법: 호출 스택 검사](../debugger/how-to-use-the-call-stack-window.md)를 참조하세요.

## <a name="change-the-execution-flow"></a>실행 흐름 변경

1. 디버거가 `Circle.Draw` 메서드 호출에서 일시 중지한 상태에서 디버거가 `base.Draw` 메서드 호출(C++의 경우 `Shape::Draw`)에서 일시 중지할 때까지 **F11** 키를 몇 번 누릅니다.

1. 마우스를 사용하여 왼쪽의 노란색 화살표(실행 포인터)를 잡고, 노란색 화살표를 `Console.WriteLine`(C++의 경우 `std::cout`) 메서드 호출의 한 줄 위로 이동시킵니다.

1. **F11** 키를 한 번 더 누릅니다.

    디버거에서 `Console.WriteLine` 메서드(C++의 경우 `std::cout`)를 다시 실행합니다.

    실행 흐름을 변경하면 디버거를 다시 시작하지 않고도 다른 코드 실행 경로를 테스트하거나 코드를 다시 실행하는 등의 작업을 수행할 수 있습니다.

    > [!WARNING]
    > 이 기능을 주의 깊게 사용해야 하는 경우가 많으며 도구 설명에 경고가 표시됩니다. 다른 경고도 표시될 수 있습니다. 포인터를 이동하면 애플리케이션을 이전 애플리케이션 상태로 되돌릴 수 없습니다.

1. **F5** 키를 눌러 애플리케이션을 계속 실행합니다.

    축하합니다. 이 자습서를 마쳤습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 디버거를 시작하고, 코드를 단계별로 실행하며, 변수를 검사하는 방법을 알아보았습니다. 더 많은 정보에 대한 링크와 함께 디버거 기능에 대해 개략적으로 살펴보는 것이 좋습니다.

> [!div class="nextstepaction"]
> [디버거 팁과 요령](../debugger/debugger-tips-and-tricks.md)
