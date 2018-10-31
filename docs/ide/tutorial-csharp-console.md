---
title: Visual Studio에서 C# 콘솔 앱 시작
description: Visual Studio에서 C# 콘솔 앱을 만드는 방법을 단계별로 알아봅니다.
ms.custom: ''
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: ad1ee95cb9cc754261502e7377cde6c91e5befce
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859512"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>자습서: Visual Studio에서 C# 콘솔 앱 시작

C#에 대한 이 자습서에서는 Visual Studio를 사용해서 콘솔 앱을 만들어 실행하고, 그 과정에서 [Visual Studio IDE(통합 개발 환경)](visual-studio-ide.md)의 일부 기능을 살펴봅니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기

먼저 C# 응용 프로그램 프로젝트를 만듭니다. 아무 것도 추가하지 않아도 필요한 모든 템플릿 파일과 함께 프로젝트 형식이 제공됩니다.

1. Visual Studio 2017을 엽니다.

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 차례로 선택합니다.

3. **새 프로젝트** 대화 상자의 왼쪽 창에서 **C#** 을 확장한 후 **.NET Core**를 선택합니다. 가운데 창에서 **콘솔 앱(.NET Core)** 을 선택합니다. 그런 다음, 파일 이름을 *Calculator*로 지정합니다.

   ![Visual Studio IDE의 새 프로젝트 대화 상자의 콘솔 앱(.NET Core) 프로젝트 템플릿](../ide/media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>(선택 사항) 작업 그룹 추가

**콘솔 앱(.NET Core)** 프로젝트 템플릿이 표시되지 않는 경우, **.NET Core 플랫폼 간 개발** 워크로드를 추가하여 얻을 수 있습니다. 컴퓨터에 Visual Studio 2017 업데이트가 설치되었는지 여부에 따라 다음 두 방법 중 하나로 이 워크로드를 추가할 수 있습니다.

#### <a name="option-1-use-the-new-project-dialog-box"></a>옵션 1: 새 프로젝트 대화 상자 사용

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Studio 설치 관리자 열기** 링크를 선택합니다.

   ![새 프로젝트 대화 상자에서 Visual Studio 설치 관리자 열기 링크 선택](../ide/media/csharp-open-visual-studio-installer-generic-dark.png)

1. Visual Studio 설치 관리자가 시작됩니다. **.NET Core 플랫폼 간 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

   ![Visual Studio Installer에서 .NET Core 플랫폼 간 개발 워크로드](../ide/media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>옵션 2: 도구 메뉴 모음 사용

1. **새 프로젝트** 대화 상자를 취소하고 나가 상단 메뉴 모음에서 **도구** > **도구 및 기능 가져오기**를 선택합니다.

1. Visual Studio 설치 관리자가 시작됩니다. **.NET Core 플랫폼 간 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

## <a name="create-a-c-console-calculator-app"></a>“C# 콘솔 계산기” 앱 만들기

1. Visual Studio 2017을 열고 상단 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **C#** 을 확장한 후 **.NET Core**를 선택합니다. 가운데 창에서 **콘솔 앱(.NET Core)** 을 선택합니다. 그런 다음, 파일 이름을 *Calculator*로 지정합니다.

1. 코드 편집기에 다음 코드를 입력하거나 붙여넣습니다.

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then instantiate to zero
                double num1 = 0; double num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToDouble(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToDouble(Console.ReadLine());

                // Ask the user to choose an option
                Console.WriteLine("Choose an option from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                // Use a switch statement to do the math
                switch (Console.ReadLine())
                {
                    case "a":
                        Console.WriteLine($"Your result: {num1} + {num2} = " + (num1 + num2));
                        break;
                    case "s":
                        Console.WriteLine($"Your result: {num1} - {num2} = " + (num1 - num2));
                        break;
                    case "m":
                        Console.WriteLine($"Your result: {num1} * {num2} = " + (num1 * num2));
                        break;
                    case "d":
                        // Ask the user to enter a non-zero divisor until they do so
                        while (num2 == 0)
                        {
                            Console.WriteLine("Enter a non-zero divisor: ");
                            num2 = Convert.ToDouble(Console.ReadLine());
                        }
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                    // Return text for an incorrect option entry
                    default:
                        Console.WriteLine("That is an incorrect option entry, please try again.");
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```

   `static void Main(string[] args)` 뒤에 오는 코드는 다음 스크린샷과 같아야 합니다.

   ![C# 콘솔 계산기를 표시하는 코드 편집기](../ide/media/csharp-console-calculator-code.png)

1. 프로그램을 실행할 **계산기**를 선택하거나 **F5** 키를 누릅니다.

   ![계산기 단추를 선택하여 도구 모음에서 앱을 실행합니다.](../ide/media/csharp-console-calculator-button.png)

1. 콘솔 창에 앱을 표시합니다. 프롬프트를 따르면 앱이 다음 스크린샷과 유사하게 표시되어야 합니다.

    ![수행할 작업에 대한 프롬프트가 포함된 Caluculator 앱이 표시된 콘솔 창](../ide/media/csharp-console-calculator.png)

### <a name="close-the-app"></a>앱 닫기

1. 계산기 앱을 닫으려면 아무 키나 누릅니다.

1. Visual Studio에서 **출력** 창을 닫습니다.

   ![Visual Studio에서 출력 창 닫기](../ide/media/csharp-calculator-close-output-pane.png)

1. Visual Studio를 닫습니다.

## <a name="quick-answers-faq"></a>빠른 답변 FAQ

몇 가지 주요 개념을 강조 표시하는 빠른 FAQ는 다음과 같습니다.

### <a name="what-is-c"></a>C#이란?

C#은 .NET Framework 및 .NET Core에서 실행되는 형식이 안전한 프로그래밍 언어입니다. C#을 사용하여 Windows 응용 프로그램, 클라이언트-서버 응용 프로그램, 데이터베이스 응용 프로그램, XML Web services, 분산 구성 요소 등을 만들 수 있습니다.

### <a name="what-is-visual-studio"></a>Visual Studio란?

Visual Studio는 개발자를 위한 통합 개발 생산성 도구입니다. 프로그램과 응용 프로그램을 만드는 데 사용할 수 있는 프로그램으로 생각하면 됩니다.

### <a name="what-is-a-console-app"></a>콘솔 앱이란?

콘솔 앱은 입력을 받고 명령줄 창, 즉 콘솔에 출력을 표시합니다.

### <a name="what-is-net-core"></a>.NET Core란?

.NET Core는 .NET Framework의 다음 진화 단계입니다. NET Framework는 프로그래밍 언어 전체에서 코드를 공유할 수 있게 했고 .NET Core는 플랫폼 간에 코드를 공유하는 기능을 더합니다. 게다가 오픈 소스입니다.

.NET Framework 및 .NET Core 둘 다에 미리 빌드된 기능 라이브러리가 포함되어 있습니다. 사용자 코드를 실행할 가상 머신 역할을 하는 CLR(공용 언어 런타임)도 포함합니다.

## <a name="next-steps"></a>다음 단계

축하합니다. 이 자습서를 마쳤습니다. 자세히 알아보려면 다음 자습서를 계속 진행하세요.

> [!div class="nextstepaction"]
> [C# 자습서](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>참고 항목

* [초보자를 위한 C# 기본 사항 비디오 과정](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)
