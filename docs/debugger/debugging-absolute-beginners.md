---
title: 초보자를 위한 코드 디버깅
description: 처음으로 디버깅 하는 경우 Visual Studio를 사용 하 여 디버깅 모드에서 앱을 실행 하는 데는 몇 가지 원칙에 알아봅니다.
ms.custom: ''
ms.date: 07/06/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8cba770195ced84083e67ae42afbef53631e5ba1
ms.sourcegitcommit: 522ba712c0d625e51352506146b0556414681964
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37890216"
---
# <a name="how-to-debug-for-absolute-beginners"></a>초보자를 위한 디버깅 하는 방법

실패 하지 않고 소프트웨어 개발자로 서 작성 하는 코드를 항상 하지 예상 작업을 수행 하도록 합니다. 경우에 따라 완전히 다르게 않습니다! 다음 태스크는 그 이유를 파악 하는 것이 문제가 발생 하면 되어 있더라도에서는 시간에 대 한 코드에서 응시 하면서 유지 하는 것을 생각할 수도 있겠지만, 훨씬 더 쉽고 효율적으로 디버깅 도구를 사용 하거나 디버거.

디버거, 아쉽게도 문제 또는 모든 "버그" 코드에 노출 마술 수 있습니다. *디버깅* 단계별 디버깅 도구에서 코드를 실행 하는 방법 등 Visual Studio에서 프로그래밍 실수를 만든 정확한 지점을 찾습니다. 다음 코드를 변경 해야 하는 수정 이해와 디버깅 도구를 사용 하면 프로그램 실행을 계속할 수 있도록 임시로 변경 합니다.

효과적으로 디버거를 사용 하 여 시간과 자세한 연습을 사용 하는 기술 이기도 하지만 모든 소프트웨어 개발자를 위한 기본 작업은 궁극적으로. 이 문서에서는 다음 디버깅의 핵심 원리를 소개 하 고 시작 하기 위한 팁을 제공 합니다.

## <a name="clarify-the-problem-by-asking-yourself-the-right-questions"></a>직접 질문을 요청 하 여 문제를 명확히 합니다.

수정 하려고 하기 전에를 실행 하는 문제를 명확 하 게 도움이 됩니다. 실행 하는 이미 문제가 코드에서 하는 것이 기대를 고, 그렇지 않습니다 수 여기 하려는 디버깅 하는 방법을 파악! 따라서 디버깅을 시작 하기 전에 해결 하고자 하는 문제를 파악 했으므로 있는지 확인 합니다.

* 예상 된 코드 작업을 수행 하 시겠습니까?

* 대신 어떻게 되었습니까?

    앱을 실행 하는 동안 오류 (예외)를 실행 하면 장점이 될 수 있습니다! 예외는 일반적으로 몇 가지 종류의 오류 코드를 실행 하는 경우에 발생 한 예기치 않은 이벤트입니다. 디버깅 도구 예외가 발생 한 코드의 정확한 위치로 이동할 수 및 가능한 수정 사항 조사 하는 데 도움이 됩니다.

    다른 문제가 발생 한 경우 문제의 증상이 무엇입니까? 생각 하는 이미 코드에서이 문제가 발생 한 위치? 예를 들어 일부 텍스트를 표시 하는 코드를 텍스트에 올바르지 않습니다 하지만 알 수는 데이터가 잘못 되었거나 표시 텍스트를 설정 하는 코드에 버그는 몇 가지 있습니다. 디버거에서 코드를 단계별로 실행 하 여 각 변경 방법과 잘못 된 값이 할당 된 경우에 정확 하 게 검색 하 여 변수를 검사할 수 있습니다.

## <a name="examine-your-assumptions"></a>한 가정을 검토합니다

버그 또는 오류를 조사 하기 전에 발생 하는 특정 결과 예상 하는 가정이 생각 하면 됩니다. 숨김 또는 알 수 없는 가정을 디버거에서 오른쪽 문제의 원인을 찾는 경우에 문제를 식별 하는 방해 가져올 수 있습니다. 가능한 가정의 긴 목록이 있을 수 있습니다. 다음은 몇 가지 질문이 가정이 올바른지 점검 하는 합니다.

* 올바른 API (즉, 오른쪽 개체, 함수, 메서드 또는 속성)를 사용 중 입니까? 사용 중인 API 수 생각 수행 하는 것을 수행 하지 않습니다. (디버거에서 API 호출을 검토 한 후 수정 해야 올바른 API를 안전 하 게 식별할 설명서 여정 합니다.)

* API을 올바르게 사용 중 입니까? 아마도 오른쪽 API를 사용 해도 올바른 방법으로 사용 하지 않았습니다.

* 코드에 오타가 생기지 포함 되어 있습니까? 변수 이름의 간단한 맞춤법 오류와 같은 몇 가지 오타 참조 변수를 사용 하려면 먼저 선언 되지 않아도 되는 언어를 사용 하는 경우에 특히 어려울 수 있습니다.

* 않은 코드를 변경 하 고 표시 되는 문제에 관련 없는 것으로 가정?

* 개체 또는 특정 값 (또는 특정 형식의 값)를 포함 하는 변수를 예상 않은 실제로 내용 다릅니다.

* 코드의 의도 알 수 있을까요? 이 코드를 다른 사람이 디버그 하기가 어려워질의 합니다. 코드 없는 경우 있기 시간 learning 정확 하 게 코드의 수행 기능 효과적으로 디버그할 수 있으려면 소비 해야 할 수 있습니다.

    > [!TIP]
    > 코드를 작성할 때 작은 작동 하는 코드를 사용 하 여 시작! (좋은 샘플 코드는 유용한 여기.) 경우에 따라 코드의 대규모 또는 복잡 한 집합을 달성 하기 위해 시도 하는 핵심 작업을 보여 주는 코드의 작은 부분부터 시작 하 여 해결 하려면 쉽습니다. 그런 다음 수정 하거나 코드를 점진적으로 추가 하 여 오류에 대 한 각 지점에서 테스트 수 있습니다.

한 가정을 느끼지, 하 여 코드에서 문제를 찾는 데 걸리는 시간을 줄일 수 있습니다. 또한 문제를 해결 하는 데 걸리는 시간을 줄일 수 있습니다.

## <a name="step-through-your-code-in-debugging-mode-to-find-where-the-problem-occurred"></a>문제가 발생 한 위치를 찾으려면 모드 디버깅에서 코드를 단계별로 실행

일반적으로 앱을 실행 하면 오류 및 표시 잘못 된 결과 코드를 실행 한 후에 됩니다. 프로그램 수 또한 원인을 없이 예기치 않게 종료 됩니다.

라고도 디버거 내에서 앱 실행 *디버깅 모드*는 디버거 적극적으로 모니터링 하는 프로그램 실행 될 때 발생 하는 것을 의미 합니다. 또한 언제 든 지 해당 상태를 검사 하는 데 발생 하는 대로 모든 세부 정보를 줄 단위로 코드를 단계별로 실행 한 다음 앱을 일시 중지할 수 있습니다.

Visual Studio에서 사용 하 여 디버깅 모드로 전환 **F5** (또는 **디버그** > **디버깅 시작** 메뉴 명령 또는 **디버깅 시작**  단추 ![디버깅 시작](../debugger/media/dbg-tour-start-debugging.png "디버깅 시작")) 디버그 도구 모음에 있습니다. 예외가 발생 하는 경우 Visual Studio의 예외 도우미 예외 발생 및 기타 유용한 정보를 제공 합니다. 여기서 정확한 지점으로 이동 합니다.

예외가 받지 수 있을 것 좋습니다 코드의 문제를 검색할 수 있는 위치입니다. 이 사용 하는 *중단점* 직접 코드를 더 신중 하 게 검사 하는 기회를 제공 하 고 디버거를 사용 합니다. 중단점은 신뢰할 수 있는 디버깅의 가장 기본적이 고 필수적인 기능입니다. 중단점 Visual Studio 변수의 값 또는 메모리의 동작 또는 코드 실행 되는 시퀀스에서 확인을 수행할 수 있도록 실행 중인 코드를 일시 중지할지를 나타냅니다.

Visual Studio에서 코드 줄 옆에 있는 왼쪽된 여백을 클릭 하 여 중단점을 신속 하 게 설정할 수 있습니다. 또는 키를 눌러 줄에 커서를 놓고 **F9**합니다.

이러한 개념에 설명 하에서는 과정을 안내 이미 몇 가지 버그를가지고 있는 몇 가지 예제 코드입니다. 에서는 C#을 사용 하면서 디버깅 기능에 적용할 Visual Basic, c + +, JavaScript, Python 및 기타 지원 되는 언어.

### <a name="create-a-sample-app-with-some-bugs"></a>몇 가지 버그) (사용 하는 샘플 앱 만들기

다음으로, 몇 가지 버그가 있는 응용 프로그램을 만듭니다.

1. Visual Studio를 설치 하 고 하나를 사용 하도록 해야 합니다. **NET 데스크톱 개발** 워크 로드 또는. **.NET Core 플랫폼 간 개발용** 워크 로드가 설치 된 형식에 앱에 따라 만들려고 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

    워크 로드를 설치 하지만 이미 Visual Studio를 클릭 해야 **도구가** > **도구 및 기능 가져오기**합니다. Visual Studio 설치 관리자가 시작됩니다. 선택 합니다. **NET 데스크톱 개발** (또는. **.NET Core 플랫폼 간 개발용**) 작업, 선택한 **수정**합니다.

1. Visual Studio를 열고 선택한 **파일** > **새로 만들기** > **프로젝트**합니다.

1. 응용 프로그램 코드에 대 한 템플릿을 선택 합니다.

    .NET Framework에 대 한에 **새 프로젝트** 대화 상자에서 **Visual C#** 를 **Windows Desktop** 선택한 다음 가운데 창 select 설치된템플릿섹션에서 **콘솔 앱 (.NET Framework)** 합니다.

    .NET core의 경우에 **새 프로젝트** 대화 상자를 선택 **Visual C#**, **.NET Core** 선택한 다음 가운데 창의 설치 된 템플릿 섹션에서 선택  **콘솔 앱 (.NET Core)** 합니다.

    이러한 템플릿이 보이지 않으면 적절 한 워크 로드를 설치 해야 합니다 (이전 단계 참조).

1. 에 **이름을** 필드에 입력 **ConsoleApp FirstApp** 클릭 **확인**합니다.

    Visual Studio 솔루션 탐색기 오른쪽 창에 나타나는 콘솔 프로젝트를 만듭니다.

1. *Program.cs*, 모든 기본 코드를 다음 코드로 바꿉니다.

    ```csharp
    using System;
    using System.Collections.Generic;
    
    namespace ConsoleApp_FirstApp
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Welcome to Galaxy News!");
                IterateThroughList();
                Console.ReadKey();
            }
    
            private static void IterateThroughList()
            {
                var theGalaxies = new List<Galaxy>
            {
                new Galaxy() { Name="Tadpole", MegaLightYears=400, GalaxyType=new GType('S')},
                new Galaxy() { Name="Pinwheel", MegaLightYears=25, GalaxyType=new GType('S')},
                new Galaxy() { Name="Cartwheel", MegaLightYears=500, GalaxyType=new GType('L')},
                new Galaxy() { Name="Small Magellanic Cloud", MegaLightYears=.2, GalaxyType=new GType('I')},
                new Galaxy() { Name="Andromeda", MegaLightYears=3, GalaxyType=new GType('S')},
                new Galaxy() { Name="Maffei 1", MegaLightYears=11, GalaxyType=new GType('E')}
            };
    
                foreach (Galaxy theGalaxy in theGalaxies)
                {
                    Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears + ",  " + theGalaxy.GalaxyType);
                }
    
                // Expected Output:  
                //  Tadpole  400,  Spiral 
                //  Pinwheel  25,  Spiral 
                //  Cartwheel, 500,  Lenticular
                //  Small Magellanic Cloud .2,  Irregular
                //  Andromeda  3,  Spiral
                //  Maffei 1,  11,  Elliptical
            }
        }
    
        public class Galaxy
        {
            public string Name { get; set; }
    
            public double MegaLightYears { get; set; }
            public object GalaxyType { get; set; }
    
        }
    
        public class GType
        { 
            public GType(char type)
            {
                switch(type)
                {
                    case 'S':
                        MyGType = Type.Spiral;
                        break;
                    case 'E':
                        MyGType = Type.Elliptical;
                        break;
                    case 'l':
                        MyGType = Type.Irregular;
                        break;
                    case 'L':
                        MyGType = Type.Lenticular;
                        break;
                    default:
                        break;
                }
            }
            public object MyGType { get; set; }
            private enum Type { Spiral, Elliptical, Irregular, Lenticular}
        }
    }
    ```

    이 코드는 의도 galaxy 형식과 galaxy, 거리 galaxy 이름 목록에 모두 표시 됩니다. 가 디버깅 하려면 코드의 의도 이해 해야 합니다. 출력에 표시 하려는 목록에서 한 줄의 형식은 다음과 같습니다.

    *galaxy 이름을*, *거리*합니다 *galaxy 형식*합니다.

### <a name="run-the-app"></a>앱 실행

1. 키를 눌러 **F5** 또는 **디버깅 시작** 단추 ![디버깅 시작](../debugger/media/dbg-tour-start-debugging.png "디버깅 시작") 코드 편집기 위쪽에 있는 디버그 도구 모음에서.

    앱이 시작 되는 디버거에 의해 우리에 게 표시 된 예외가 없습니다 및 합니다. 그러나 콘솔 창에 나오는 출력 기대와 다르면 됩니다. 예상된 된 출력은 다음과 같습니다.

    ```
    Tadpole  400,  Spiral 
    Pinwheel  25,  Spiral 
    Cartwheel, 500,  Lenticular
    Small Magellanic Cloud .2,  Irregular
    Andromeda  3,  Spiral
    Maffei 1,  Elliptical
    ```

    하지만이 대신 표시 합니다.

    ```
    Tadpole  400,  ConsoleApp_FirstApp.GType 
    Pinwheel  25,  ConsoleApp_FirstApp.GType 
    Cartwheel, 500,  ConsoleApp_FirstApp.GType
    Small Magellanic Cloud .2,  ConsoleApp_FirstApp.GType
    Andromeda  3,  ConsoleApp_FirstApp.GType
    Maffei 1, 11,  ConsoleApp_FirstApp.GType
    ```

    출력에서 코드를 찾고 있음을 알고 `GType` galaxy 유형을 저장 하는 클래스의 이름입니다. 실제 galaxy 형식 (예: "나선형")을 표시 하려는 클래스 이름이 없습니다.

### <a name="debug-the-app"></a>앱 디버그

1. 실행 중인 앱을 사용 하 여 옆에 왼쪽된 여백을 클릭 하 여 중단점을 설정 합니다 `Console.WriteLine` 이 줄의 코드에서 메서드 호출 합니다.

    ```csharp
    foreach (Galaxy theGalaxy in theGalaxies)
    {
        Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears + ",  " + theGalaxy.GalaxyType);
    }    
    ```

    중단점을 설정 하는 경우, 왼쪽된 여백에 빨간 점이 표시 됩니다.

    출력의 문제를 표시 하기 때문에 디버거에서 출력을 설정 하는 이전 코드를 살펴보면 디버깅 시작 합니다.

1. 클릭 합니다 **다시 시작** ![앱 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 디버그 도구 모음에서 단추 (**Ctrl** + **Shift**   +  **F5**).

    앱 사용자가 설정한 중단점에서 일시 중지 합니다. 노란색 hightlighting 나타냅니다 디버거가 일시 중지 됨 (노란색 줄의 코드는 아직 실행).

1. 마우스로 합니다 `GalaxyType` 오른쪽의 한 렌치 아이콘의 왼쪽에 다음 변수 확장 `theGalaxy.GalaxyType`합니다. 표시 `GalaxyType` 속성이 포함 되어 `MyGType`, 속성 값을로 설정 되 고 `Spiral`입니다.

    ![변수를 검사 합니다.](../debugger/media/beginners-inspect-variable.png)

    "나선형" 실제로 올바른 값을 콘솔에 인쇄 하려면 예상 했던 되었습니다. 따라서 것이 좋지만이 코드에서이 값을 응용 프로그램을 실행 하는 동안 액세스할 수 있습니다. 이 시나리오에서는 잘못 된 API를 사용 합니다. 살펴보겠습니다 경우 디버거에서 코드를 실행 하는 동안 수정할 수 있습니다.

1. 동일한 코드에서 여전히 디버깅 하는 동안 커서를 놓습니다 끝 `theGalaxy.GalaxyType` 로 변경 하 고 `theGalaxy.GalaxyType.MyGType`입니다. 이 변경, 만들 수 있지만이 코드를 컴파일할 수 없습니다 것을 나타내는 오류 코드 편집기를 보여줍니다.

    ![구문 오류](../debugger/media/beginners-edit.png)

1. 클릭 **편집할** 에 **편집 하며 계속 하기** 메시지 상자입니다. 이제의 오류 메시지를 표시 합니다 **오류 목록** 창입니다. 나타내는 오류를 `'object'` 에 대 한 정의 포함 하지 않습니다 `MyGType`합니다.

    ![구문 오류](../debugger/media/beginners-no-definition.png)

    형식의 개체를 사용 하 여 각 galaxy 설정 하는 경우에 `GType` (있는 합니다 `MGType` 속성), 디버거를 인식 하지 않습니다는 `theGalaxy` 형식의 개체와 개체 `GType`. 무슨 일이죠? Galaxy 형식을 설정 하는 코드를 확인 해야 합니다. 이렇게 하면 표시는 `GType` 클래스의 속성을 확실 하 게에 `MyGType`, 오른쪽 왔지만 것입니다. 에 대 한 오류 메시지 `object` 단서; 것으로 밝혀졌습니다 유형이 표시 언어 인터프리터 형식의 개체로 `object` 형식의 개체 대신 `GType`합니다.

1. 찾을 galaxy 형식 설정과 관련 된 코드를 살펴보는 `GalaxyType` 의 속성을 `Galaxy` 으로 클래스를 지정 `object` 대신 `GType`합니다.

    ```csharp
    public object GalaxyType { get; set; }     
    ```

1. 앞의 코드를 변경 합니다.

    ```csharp
    public GType GalaxyType { get; set; }     
    ```

1. 클릭 합니다 **다시 시작** ![앱 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 디버그 도구 모음에서 단추 (**Ctrl** + **Shift**   +  **F5**) 코드를 다시 컴파일하고 다시 시작 합니다.

    이제 때 디버거가 일시 중지 `Console.WriteLine`를 마우스로 가리키면 `theGalaxy.GalaxyType.MyGType`, 값을 제대로 설정 되어 있는지 확인 합니다.

1. 왼쪽된 여백에 중단점 원을 클릭 하 여 중단점을 제거 (또는 마우스 오른쪽 단추로 클릭 하 고 선택 **중단점** > **중단점 삭제**)을 누릅니다 **F5** 를 계속 합니다.

    앱을 실행 하 고 출력을 표시 합니다. 이 매우 이제 보이지만 점은; 알게 수행 콘솔 출력에서 불규칙 한 galaxy로 나타나도록 작은 Magellanic Cloud galaxy 하는데 전혀 없는 galaxy 형식을 보여 줍니다.

    ```
    Tadpole  400,  Spiral 
    Pinwheel  25,  Spiral 
    Cartwheel, 500,  Lenticular
    Small Magellanic Cloud .2,
    Andromeda  3,  Spiral
    Maffei 1,  Elliptical
    ```

1. 이 코드 줄에 중단점을 설정 합니다.

    ```csharp
    public GType(char type)
    ```

    이 코드는 galaxy 형식이 설정 되어 있는 좀 더 자세히 살펴보고 하고자 합니다.

1. 클릭 합니다 **다시 시작** ![앱 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 디버그 도구 모음에서 단추 (**Ctrl** + **Shift**   +  **F5**)를 다시 시작 합니다.

    디버거는 중단점을 설정한 코드 줄에서 일시 중지 합니다.  

1. 마우스로 `type` 변수입니다. 값이 표시 `S` (코드 다음에 오는 문자). 값에 관심이 있다면 `I`비정상적인 galaxy 형식이 알고 있으므로, 합니다.

1. 키를 눌러 **F5** 마우스로 및는 `type` 다시 변수입니다. 값이 표시 될 때까지이 단계를 반복 `I` 에 `type` 변수입니다.

    ![변수를 검사 합니다.](../debugger/media/beginners-inspecting-data.png)

1. 이제 키를 누릅니다 **F11** (**디버그** > **단계씩** 또는 **단계씩** 디버그 도구 모음 단추).

    **F11** 디버거를 앞으로 이동 (및 코드를 실행) 한 번에 하나의 문입니다. **F10** (**프로시저 단위 실행**)은 유사한 명령 및 디버거를 사용 하는 방법을 학습 하는 경우 둘 다는 매우 유용 합니다.

1. 키를 눌러 **F11** 의 코드 줄에서 중지 하기 전까지 `switch` 'I'의 값에 대 한 문입니다. 여기에 오타가에서 발생 하는 문제 해결. 설정으로 이동 하는 코드를 예상 `MyGType` 를 비정상으로 galaxy 형식이 아니라 디버거 대신이 코드를 완전히 건너뛰고 및 일시 중지를 `default` 섹션을 `switch` 문.

    ![오타를 찾으려면](../debugger/media/beginners-typo.png)

    코드를 살펴보면 표시를 잘못 입력 된 `case 'l'` 문입니다. 해야 `case 'I'`합니다.

1. 코드에서 클릭 `case 'l'`, 바꿉니다 ' case 'I'입니다.

1. 중단점을 제거 하 고 클릭 합니다 **다시 시작** 앱을 다시 시작 하는 단추입니다.

    이제 버그 수정 및 예상 출력을 참조 하세요!

    앱을 완료 하려면 아무 키나를 누릅니다.

## <a name="summary"></a>요약

디버거를 사용 하는 문제를 표시 하는 경우 및 [명령 단계](../debugger/navigating-through-code-with-the-debugger.md) 와 같은 **F10** 및 **F11** 문제가 있는 코드 영역을 찾으려고 합니다.

> [!NOTE]
> 문제가 발생 하는 코드의 특정 영역을 식별 하기 어려운 경우 문제가 발생 하기 전에 실행 되는 코드에 중단점을 설정 하 고 문제가 표시 될 때까지 다음 단계 명령을 사용 하 여 매니페스트 합니다. 사용할 수도 있습니다 [추적점](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints) 기록할 메시지를 합니다 **출력** 창입니다. 기록된 된 메시지 (살펴보고 메시지 아직 기록 되지 않은 확인!), 문제가 있는 코드 영역을 종종 격리할 수 있습니다. 범위를 좁히는 것이 프로세스를 여러 번 반복 해야 합니다.

문제가 있는 코드 영역을 찾으면 디버거 조사를 사용 하 고 있습니다. 문제의 원인을 찾으려고 디버거에서 앱을 실행 하는 동안 문제 코드를 검사 합니다.

* [변수 검사](../debugger/view-data-values-in-data-tips-in-the-code-editor.md) 포함 해야 하는 값의 형식에 포함 되어 있는지 여부를 확인 합니다. 잘못 된 값을 찾을 경우 잘못 된 값이 설정 하는 위치 확인 (값이 설정 된 위치를 찾으려면 해야 하거나 디버거를 다시 시작을 확인 합니다 [호출 스택](../debugger/how-to-use-the-call-stack-window.md), 또는 둘 다).

* 응용 프로그램 해야 하는 코드를 실행 하 고 있는지 확인 합니다. (예를 들어 galaxy 유형을 비정상으로 설정 하려면 switch 문 용 코드를 예상 샘플 응용 프로그램에서 하지만 앱의 오타로 인해 코드를 건너뜁니다.)

> [!TIP]
> 디버거를 사용 하 여 버그를 찾는 데 도움이 됩니다. 디버깅 도구에서 버그를 찾을 수 *하기* 코드의 의도 인식 하는 경우에 합니다. 만 도구를 개발자, express는 의도 하는 경우 코드의 의도 파악할 수 있습니다. 작성할 [단위 테스트](../test/improve-code-quality.md) 그 방법은 됩니다.

## <a name="next-steps"></a>다음 단계

이 문서에서는 몇 가지 일반적인 디버깅 개념에 알아보았습니다. 다음으로 Visual Studio를 사용 하 여 디버그 하는 방법 학습을 시작할 수 있습니다.

> [!div class="nextstepaction"]
> [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)
