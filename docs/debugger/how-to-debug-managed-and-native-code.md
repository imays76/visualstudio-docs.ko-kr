---
title: '자습서: (혼합된 모드) 관리 및 네이티브 코드 디버그'
description: 혼합 모드 디버깅을 사용 하 여.NET Core 또는.NET Framework 앱에서 네이티브 DLL을 디버그 하는 방법 알아보기
ms.custom: ''
ms.date: 11/02/2018
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
ms.openlocfilehash: 121584611dcf0f25fa1f32a616253ecdecf04332
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51295763"
---
# <a name="tutorial-debug-managed-and-native-code-in-the-same-debugging-session"></a>자습서: 동일한 디버깅 세션에서 관리 및 네이티브 코드 디버깅

Visual Studio를 사용 하면 혼합 모드 디버깅 이라고 하는 디버깅 세션에서 둘 이상의 디버거 형식을 사용 하도록 설정 합니다. 이 자습서에서는 단일 디버깅 세션에서 관리 및 네이티브 코드 디버깅에 알아봅니다. 

이 자습서에는 관리 되는 앱에서 네이티브 코드를 디버깅 하는 방법을 보여줍니다. 하지만 할 수도 있습니다 [네이티브 앱에서 관리 되는 코드를 디버그](../debugger/how-to-debug-in-mixed-mode.md)합니다. 디버거는 혼합 모드 디버깅에서 디버깅 등의 다른 형식에서는 [Python과 네이티브 코드](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md), 및 ASP.NET과 같은 앱 형식에 스크립트 디버거를 사용 합니다.

이 자습서에서 다음을 수행합니다.

> [!div class="checklist"]
> * 간단한 네이티브 DLL 만들기
> * DLL을 호출 하기 위한 간단한.NET Core 또는.NET Framework 앱 만들기
> * 혼합 모드 디버깅 구성
> * 디버거를 시작 합니다.
> * 관리 되는 앱에서 중단점이 적중
> * 네이티브 코드를 한 단계씩

## <a name="prerequisites"></a>전제 조건

Visual Studio 다음 워크 로드를 사용 하 여 설치 되어 있어야 합니다.
- **C + +를 사용한 데스크톱 개발**
- 어느 **.NET 데스크톱 개발** 하거나 **.NET Core 플랫폼 간 개발용**만들려는 어떤 유형의 앱에 따라 합니다.

Visual Studio가 없는 경우으로 이동 합니다 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 체험 용으로 설치 하는 페이지입니다.

Visual Studio가 설치 되어 있지만 선택 필요한 워크 로드에 없는 경우 **Visual Studio 설치 관리자 열기** Visual Studio의 왼쪽된 창에서 **새 프로젝트** 대화 상자. Visual Studio 설치 관리자에서 필요한 및 선택한 워크 로드를 선택 **수정**합니다.

## <a name="create-a-simple-native-dll"></a>간단한 네이티브 DLL 만들기

**DLL 프로젝트에 대 한 파일을 만들려면:**

1. Visual Studio에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. 에 **새 프로젝트** 대화 상자의 **Visual c + +** 를 선택 **다른**를 선택한 후 **빈 프로젝트** 가운데 창에서.

1. 에 **이름을** 필드에 입력 **Mixed_Mode_Debugging**를 선택한 후 **확인**합니다.

   Visual Studio가 빈 프로젝트를 만들고에 표시 **솔루션 탐색기**합니다.

1. **솔루션 탐색기**를 선택 **소스 파일**를 선택한 후 **프로젝트** > **새 항목 추가**합니다. 또는 마우스 오른쪽 단추로 클릭 **소스 파일** 선택한 **추가** > **새 항목**합니다. 

1. 에 **새 항목** 대화 상자에서 **c + + 파일 (.cpp)** 합니다. 형식 **Mixed_Mode.cpp** 에 **이름** 필드를 선택한 후 **추가**합니다.

    새 c + + 파일을 추가 하는 visual Studio **솔루션 탐색기**합니다.

1. 다음 코드를 복사 *Mixed_Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. **솔루션 탐색기**를 선택 **헤더 파일**를 선택한 후 **프로젝트** > **새 항목 추가**합니다. 또는 마우스 오른쪽 단추로 클릭 **헤더 파일** 선택한 **추가** > **새 항목**합니다. 

1. 에 **새 항목** 대화 상자에서 **헤더 파일 (.h)** 합니다. 형식 **Mixed_Mode.h** 에 **이름** 필드를 선택한 후 **추가**합니다.

   새 헤더 파일을 추가 하는 visual Studio **솔루션 탐색기**합니다.

1. 다음 코드를 복사 *Mixed_Mode.h*:

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

1. 선택 **파일** > **모두 저장** 누르거나 **Ctrl**+**Shift**+**S**  파일을 저장 합니다.

**구성 하 고 DLL 프로젝트를 빌드합니다.**

1. Visual Studio 도구 모음에서 선택 **디버그** 구성 하 고 **x86** 하거나 **x64** 플랫폼입니다. 호출 앱에는 항상 64 비트 모드로 실행 되는.NET Core를 되 면 선택 **x64** 플랫폼으로 합니다.

1. **솔루션 탐색기**를 선택 합니다 **Mixed_Mode_Debugging** 프로젝트 노드를 선택 합니다 **속성** 아이콘을 또는 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.

1. 맨 위에 있는 합니다 **속성** 창 있는지 확인 합니다 **구성** 로 설정 되어 **활성** 및 **플랫폼** 항목 동일 도구 모음에서 설정: **x64**, 또는 **Win32** x86 플랫폼입니다. 

   > [!IMPORTANT]
   > 플랫폼에서 전환 하는 경우 **x86** 에 **x64** 또는 반대로 새 플랫폼에 대 한 속성을 다시 구성 해야 합니다. 

1. 아래 **구성 속성** 왼쪽된 창에서 선택 **링커** > **고급**, 옆에 드롭다운 및 **진입점 없음**을 선택 **No**합니다. 로 변경 해야 하는 경우 **No**를 선택 **적용**합니다.

1. 아래 **구성 속성**를 선택 **일반**, 및 옆에 드롭다운 목록에서 **구성 유형**선택, **동적 라이브러리 (.dll)**. 선택 **Apply**를 선택한 후 **확인**합니다.

   ![네이티브 DLL로 전환](../debugger/media/mixed-mode-set-as-native-dll.png)

1. 프로젝트를 선택 **솔루션 탐색기** 선택한 후 **빌드** > **솔루션 빌드**, 키를 눌러 **F7**를 마우스 오른쪽 단추로 클릭 프로젝트를 마우스 **빌드**합니다.

   프로젝트가 오류 없이 빌드되어야 합니다.

## <a name="create-a-simple-managed-app-to-call-the-dll"></a>DLL을 호출 하는 간단한 관리 되는 앱 만들기

1. Visual Studio에서 선택 **파일** > **새로 만들기** > **프로젝트**합니다.

   > [!NOTE]
   > 또한 기존 c + + 솔루션에 새 관리 되는 프로젝트를 추가할 수 있습니다, 새 솔루션을 만드는 더 많은 디버깅 시나리오를 지원 합니다.

1. 에 **새 프로젝트** 대화 상자에서 **시각적 C#** , 및 가운데 창에서:

   - .NET Framework 앱의 경우 선택 **콘솔 앱 (.NET Framework)** 합니다.
   
   - .NET Core 앱을 선택 **콘솔 앱 (.NET Core)** 합니다.

1. 에 **이름을** 필드에 입력 **Mixed_Mode_Calling_App**를 선택한 후 **확인**합니다.

   Visual Studio가 빈 프로젝트를 만들고에 표시 **솔루션 탐색기**합니다.

1. 모든 코드를 바꿔 *Program.cs* 다음 코드를 사용 하 여:

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
            // C:\Users\username\source\repos\Mixed_Mode_Debugging\x64\Debug\Mixed_Mode_Debugging.dll
            // Here, we show a typical path for a DLL targeting the **x86** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed_Mode_Debugging\Debug\Mixed_Mode_Debugging.dll", EntryPoint =
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

1. 새 코드 파일 경로 바꿉니다 `[DllImport]` 프로그램 파일 경로 사용 하 여 합니다 *Mixed_Mode_Debugging.dll* 방금 만든 합니다. 힌트에 대 한 코드 설명을 참조 하세요. 으로 대체 해야 합니다 *username* 자리 표시자입니다.

1. 선택 **파일** > **저장 Program.cs** 누르거나 **Ctrl**+**S** 파일을 저장 합니다.

## <a name="configure-mixed-mode-debugging"></a>혼합 모드 디버깅 구성 

### <a name="to-configure-mixed-mode-debugging-for-a-net-framework-app"></a>.NET Framework 앱에 대 한 혼합 모드 디버깅을 구성 하려면 

1. **솔루션 탐색기**를 선택 합니다 **Mixed_Mode_Calling_App** 프로젝트 노드를 선택 합니다 **속성** 아이콘을 또는 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.

1. 선택 **디버깅할** 왼쪽된 창에서 선택 합니다 **네이티브 코드 디버깅 사용** 확인란을 선택한 다음 변경 내용을 저장 하려면 속성 페이지를 닫습니다.

    ![혼합된 모드 디버깅 사용](../debugger/media/mixed-mode-enable-native-code-debugging.png)

### <a name="to-configure-mixed-mode-debugging-for-a-net-core-app"></a>.NET Core 앱에 대 한 혼합 모드 디버깅을 구성 하려면 

대부분의 Visual Studio 2017 버전을 사용 해야 하는 *launchSettings.json* .NET Core 앱에서 네이티브 코드에 대 한 혼합 모드 디버깅을 사용 하려면 프로젝트 속성 대신 파일입니다. 이 기능에 대 한 UI 업데이트를 추적 하려면이 참조 [GitHub 문제](https://github.com/dotnet/project-system/issues/1125)합니다.

1. **솔루션 탐색기**, 확장 **속성**을 연 합니다 *launchSettings.json* 파일입니다. 

   >[!NOTE]
   >기본적으로 *launchSettings.json* 상태인 *C:\Users\username\source\repos\Mixed_Mode_Calling_App\Properties*합니다. 하는 경우 *launchSettings.json* 선택가 존재 하지 않는 합니다 **Mixed_Mode_Calling_App** 프로젝트 **솔루션 탐색기** 선택한 후는 **속성** 아이콘을 또는 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 임시 변경 합니다 **디버그** 탭 및 프로젝트를 빌드합니다. 만들기는이 *launchSettings.json* 파일입니다. 수행한 변경 내용을 취소 합니다 **디버그** 탭 합니다.

1. 에 *lauchsettings.json* 파일을 다음 줄을 추가 합니다.

    ```csharp
    "nativeDebugging": true
    ```

    전체 파일은 다음과 같이 표시 됩니다.

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

## <a name="set-a-breakpoint-and-start-debugging"></a>중단점을 설정 하 고 디버깅 시작

1. 에 C# 프로젝트 열기 *Program.cs*합니다. 맨 왼쪽된 여백을 클릭, 줄을 선택 하 고 키를 눌러 코드의 다음 줄에 중단점을 설정할 **F9**, 또는 줄을 마우스 오른쪽 단추로 클릭 하 고 선택 **중단점**  >  **중단점 삽입**합니다.

    ```csharp
    int result = Multiply(7, 7);
    ```

    중단점을 설정한 왼쪽된 여백에 빨간색 원이 표시 됩니다.

1. 키를 눌러 **F5**Visual Studio 도구 모음에서 녹색 화살표를 선택 하거나 선택 **디버그** > **디버깅 시작** 디버깅을 시작 합니다.

   디버거가 설정한 중단점에서 일시 중지 합니다. 노란색 화살표는 디버거가 현재 일시 중지를 나타냅니다.

## <a name="step-in-and-out-of-native-code"></a>네이티브 코드의 시작 및 종료 단계

1. 디버깅 관리 되는 앱에서 일시 중지 하는 동안 키를 누릅니다 **F11**를 선택 하거나 **디버그** > **단계에**합니다.

   합니다 *Mixed_Mode.h* 네이티브 헤더 파일이 열리고 디버거가 일시 중지 된 노란색 화살표를 표시 합니다.

   ![네이티브 코드를 한 단계씩](../debugger/media/mixed-mode-step-into-native-code.png)

1. 이제 설정 하 고 및 중단점을 적중 하 고, 네이티브 또는 관리 코드에서 변수를 검사할 수 있습니다.

   - 해당 값을 확인 하려면 소스 코드에서 변수 위에 마우스를 가져갑니다.

   - 변수 및 해당 값을 확인 합니다 **자동** 하 고 **지역** windows.

   - 디버거에서 일시 중지 하는 동안 사용할 수도 있습니다는 **Watch** windows 및 **호출 스택** 창입니다.

1. 키를 눌러 **F11** 디버거를 한 줄 시키려는 다시 합니다.

1. 키를 눌러 **Shift**+**F11** 누르거나 **디버그** > **나가기** 실행을 계속 다시 일시 중지 하는 관리 되는 앱입니다.

1. 키를 눌러 **F5** 하거나 앱을 디버깅 하려면 녹색 화살표를 선택 합니다.

지금까지 혼합 모드 디버깅에 대 한 자습서를 완료 했습니다.

## <a name="next-step"></a>다음 단계

이 자습서에서는 혼합 모드 디버깅을 사용 하 여 관리 되는 앱에서 네이티브 코드를 디버그 하는 방법을 알아보았습니다. 다른 디버거 기능 개요를 참조 하세요.

> [!div class="nextstepaction"]
> [디버거 소개](../debugger/debugger-feature-tour.md)
