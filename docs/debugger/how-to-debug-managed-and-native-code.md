---
title: '자습서: (혼합된 모드) 관리 및 네이티브 코드 디버그'
description: 혼합된 모드 디버깅을 사용 하 여.NET Core 또는.NET Framework 앱에서 네이티브 DLL을 디버그 하는 방법 알아보기
ms.custom: ''
ms.date: 04/27/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- mixed mode debugging
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: 1f34f6af0a98e71f5feb910f84e8d67ada051ae9
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057039"
---
# <a name="tutorial-debug-managed-and-native-code-in-visual-studio"></a>자습서: Visual Studio에서 관리 및 네이티브 코드 디버그

Visual Studio를 사용 하면 혼합된 모드 디버깅 이라고 하는 둘 이상의 디버거 유형을 디버깅할 때 설정할 수 있습니다. 이 자습서에서는 단일 디버깅 세션에서 관리 및 네이티브 코드를 디버그 하는 옵션을 설정할 수 있습니다. 이 자습서에서는 관리 되는 앱에서 네이티브 코드를 디버깅 하는 방법을 보여줍니다. 하지만 반대의 경우에 수행할 수 있습니다 하 고 [네이티브 앱에서 관리 되는 코드를 디버그](../debugger/how-to-debug-in-mixed-mode.md)합니다. 디버거는 혼합된 모드 디버깅에서 디버깅 등의 다른 형식에서는 [Python과 네이티브 코드](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md) 및 ASP.NET과 같은 앱 형식에 스크립트 디버거를 사용 합니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 간단한 네이티브 DLL 만들기
> * DLL을 호출 하기 위한 간단한.NET Core 또는.NET Framework 앱 만들기
> * 디버거를 시작 합니다.
> * 관리 되는 앱에서 중단점이 적중
> * 네이티브 코드를 한 단계씩

## <a name="prerequisites"></a>전제 조건

* Visual Studio가 설치 되어 있어야 하며 **c + +를 사용한 데스크톱 개발** 워크 로드.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

    워크로드를 설치해야 하지만 이미 Visual Studio가 있는 경우 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다. Visual Studio 설치 관리자가 시작됩니다. **Node.js 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

* 수도 있어야 합니다 **.NET 데스크톱 개발** 워크 로드 또는 **.NET Core 플랫폼 간 개발용** 워크 로드가 설치를 만들려고 할 형식에 앱에 따라 합니다.

## <a name="create-a-simple-native-dll"></a>간단한 네이티브 DLL 만들기

1. Visual Studio에서 선택 **파일** > **새로 만들기** > **프로젝트**합니다.

1. 에 **새 프로젝트** 대화 상자에서 **Visual c + +** 에 **일반** 한 다음 가운데 창의 설치 된 템플릿 섹션에서 선택 **빈 프로젝트** .

1. 에 **이름을** 필드에 입력 **혼합 모드 디버깅** 클릭 **확인**합니다.

    Visual Studio에 오른쪽 창에서 솔루션 탐색기에 나타나는 빈 프로젝트를 만듭니다.

1. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 합니다 **소스 파일** 노드 c + + 프로젝트를 선택한 후 **추가** > **새 항목**를 선택한 후 **c + + 파일 (.cpp)** 합니다. 파일 이름을 **혼합 Mode.cpp**, 선택한 **추가**합니다.

    Visual Studio는 새 c + + 파일을 추가합니다.

1. 다음 코드를 복사 *혼합 Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 합니다 **헤더 파일** 노드 c + +에서 프로젝트를 선택한 후 **추가** > **새 항목**를 선택한 후  **헤더 파일 (.h)** 합니다. 파일 이름을 **혼합 Mode.h**, 선택한 **추가**합니다.

    Visual Studio 새 헤더 파일을 추가합니다.

1. 다음 코드를 복사 *혼합 Mode.h*:

    ```cpp
    #ifndef MIXED_MODE_MULTIPLY_HPP
    #define MIXED_MODE_MULTIPLY_HPP

    extern "C"
    {
        __declspec(dllexport) int __stdcall mixed_mode_multiply(int a, int b) {
            return a * b;
        }
    }
    #endif
    ```

1. 디버그 도구 모음에서 선택는 **디버그** 구성 하 고 **임의 CPU** 를 플랫폼으로,.NET core를 선택 **x64** 플랫폼으로 합니다.

    > [!NOTE]
    > .NET Core에서 선택 **x64** 플랫폼으로 합니다. .NET core 필수 이기 때문에 항상 64 비트 모드에서 실행 됩니다.

1. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 (**혼합 모드 디버깅**)를 선택 하 고 **속성**합니다.

1. 에 **속성** 페이지에서 **구성 속성** > **링커** > **고급**, 및 그런 다음 합니다 **진입점 없음** 드롭 다운 목록에서 **NO**합니다. 그런 다음 설정을 적용 합니다.

1. 에 **속성** 페이지에서 **구성 속성** > **일반**를 선택한 후 **동적 라이브러리 (.dll)** 에서 **구성 유형** 필드입니다. 그런 다음 설정을 적용 합니다.

    ![네이티브 DLL로 전환](../debugger/media/mixed-mode-set-as-native-dll.png)

1. 선택한 프로젝트를 마우스 오른쪽 단추로 클릭 **디버깅할** > **빌드**합니다.

    프로젝트가 오류 없이 빌드되어야 합니다.

## <a name="create-a-simple-net-framework-or-net-core-app-to-call-the-dll"></a>DLL을 호출 하기 위한 간단한.NET Framework 또는.NET Core 앱 만들기

1. Visual Studio에서 선택 **파일** > **새로 만들기** > **프로젝트**합니다.

1. 응용 프로그램 코드에 대 한 템플릿을 선택 합니다.

    .NET Framework에 대 한에 **새 프로젝트** 대화 상자에서 **Visual C#** 를 **Windows Desktop** 선택한 다음 가운데 창 select 설치된템플릿섹션에서 **콘솔 앱 (.NET Framework)** 합니다.

    .NET core의 경우에 **새 프로젝트** 대화 상자를 선택 **Visual C#**, **.NET Core** 선택한 다음 가운데 창의 설치 된 템플릿 섹션에서 선택  **콘솔 앱 (.NET Core)** 합니다.

1. 에 **이름을** 필드에 입력 **Mixed_Mode_Calling_App** 클릭 **확인**합니다.

    Visual Studio 솔루션 탐색기 오른쪽 창에 나타나는 콘솔 프로젝트를 만듭니다.

1. *Program.cs*, 기본 코드를 다음 코드로 바꿉니다.

    ```csharp
    using System;
    using System.Runtime.InteropServices;

    namespace Mixed_Mode_Calling_App
    {
        public class Program
        {
            // Replace the file path shown here with the
            // file path on your computer. For .NET Core, the typical (default) path
            // for a 64-bit DLL might look like this:
            // C:\Users\username\source\repos\Mixed-Mode-Debugging\x64\Debug\Mixed-Mode-Debugging.dll
            // Here, we show a typical path for a DLL targeting the **Any CPU** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed-Mode-Debugging\Debug\Mixed-Mode-Debugging.dll", EntryPoint =
            "mixed_mode_multiply", CallingConvention = CallingConvention.StdCall)]
            public static extern int Multiply(int x, int y);
            public static void Main(string[] args)
            {
                int result = Multiply(7, 7);
                Console.WriteLine("The answer is {0}", result);
                Console.ReadKey();
            }
        }
    }
    ```

## <a name="configure-mixed-mode-debugging-net-framework"></a>혼합된 모드 디버깅 (.NET Framework) 구성

1. 솔루션 탐색기에서 관리 되는 마우스 오른쪽 단추로 **Mixed_Mode_Calling_App** 프로젝트를 선택 **시작 프로젝트로 설정**합니다.

1. 관리 되는 마우스 오른쪽 단추로 클릭 **Mixed_Mode_Calling_App** 프로젝트를 선택한 후 **속성**를 선택한 후 **디버그** 왼쪽된 창에서. 선택 **네이티브 코드 디버깅 사용**, 한 다음 변경 내용을 저장 하려면 속성 페이지를 닫습니다.

    ![혼합된 모드 디버깅 사용](../debugger/media/mixed-mode-enable-native-code-debugging.png)

## <a name="configure-mixed-mode-debugging-net-core"></a>혼합된 모드 디버깅 (.NET Core)를 구성 합니다.

대부분 Visual Studio 2017의 버전을 사용 해야 사용 하 여.NET Core 앱에서 네이티브 코드에 대 한 혼합된 모드 디버깅은 *launchSettings.json* 대신 파일을 **속성** 페이지. 이 기능에 대 한 UI 업데이트를 추적 하려면이 참조 [GitHub 문제](https://github.com/dotnet/project-system/issues/1125)합니다.

1. 엽니다는 *launchSettings.json* 파일을 *속성* 폴더. 기본적으로이 위치에 파일을 찾을 수 있습니다.

    *C:\Users\<사용자 이름 > \source\repos\Mixed_Mode_Calling_App\Properties*

    파일이 없으면 프로젝트 속성을 엽니다 (관리 되는 마우스 오른쪽 단추로 클릭 **Mixed_Mode_Calling_App** 솔루션 탐색기에서 프로젝트를 마우스 **속성**). 임시 변경 합니다 **디버그** 탭 및 프로젝트를 빌드합니다. 만든 변경 내용을 취소 합니다.

1. 에 *lauchsettings.json* 파일에서 다음 속성을 추가 합니다.

    ```csharp
    "nativeDebugging": true
    ```

    따라서 예를 들어, 다음과 같은 파일에 표시 될 수 있습니다.

    ```csharp
    {
      "profiles": {
        "Mixed_Mode_Calling_App": {
          "commandName": "Project",
          "nativeDebugging": true
        }
      }
    }
    ```

## <a name="set-a-breakpoint-and-start-the-debugger"></a>중단점을 설정 하 고 디버거를 시작

1. C# 프로젝트를 엽니다 *Program.cs* 왼쪽 여백을 클릭 하 여 코드의 다음 줄에서 중단점을 설정 합니다.

    ```csharp
    int result = Multiply(7, 7);
    ```

    중단점을 설정 했는지를 나타내기 위해 왼쪽된 여백에 빨간색 원이 표시 됩니다.

1. 키를 눌러 **F5** (**디버그** > **디버깅 시작**) 디버거를 시작 합니다.

    디버거가 설정한 중단점에서 일시 중지 합니다. 노란색 화살표는 디버거가 현재 일시 중지를 나타냅니다.

## <a name="step-into-native-code"></a>네이티브 코드를 한 단계씩

1. 관리 되는 앱에서 일시 중지 하는 동안 키를 눌러 **F11** (**디버그** > **단계씩**).

    네이티브 코드와 헤더 파일이 열리고 디버거가 일시 중지 된 노란색 화살표를 표시 합니다.

    ![네이티브 코드를 한 단계씩](../debugger/media/mixed-mode-step-into-native-code.png)

    이제 수행 및 중단점을 적중 하 변수를 검사 합니다.

1. 해당 값을 확인 하려면 변수를 마우스로 가리킵니다.

1. 확인 합니다 **자동** 하 고 **지역** 변수와 해당 값을 확인 하려면 windows.

    디버거에서 일시 중지 된 동안 다른 디버거 기능을 같은 사용할 수 있습니다 합니다 **Watch** 창 및 **호출 스택** 창입니다.

1. 키를 눌러 **F11** 디버거를 한 줄 시키려는 다시 합니다.

1. 키를 눌러 **shift+f11** (**디버그** > **나가기**) 앱 실행을 계속 하려면 관리 되는 앱에서 다시 일시 중지 합니다.

1. 앱을 계속하려면 **F5** 키를 누릅니다.

    지금까지 혼합된 모드 디버깅에 대 한 자습서를 완료 했습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 혼합된 모드 디버깅을 사용 하 여 관리 되는 앱에서 네이티브 코드를 디버그 하는 방법을 알아보았습니다. 다른 디버거 기능 개요를 보려면 다음 문서를 참조 합니다.

> [!div class="nextstepaction"]
> [디버거 소개](../debugger/debugger-feature-tour.md)
