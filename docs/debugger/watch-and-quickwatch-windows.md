---
title: Visual Studio에서 변수에 대 한 조사식 설정 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 10/11/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.watch
helpviewer_keywords:
- debugging [Visual Studio], Watch window
- expressions [debugger], evaluating
- variables [debugger], evaluating
- expression evaluation
- registers, evaluating
- debugging [Visual Studio], expression evaluation
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad08799c0dce3792e096291dfaf62d52e2515df4
ms.sourcegitcommit: 48bc8492973e93612e5afaba3b47d0f98aecf97c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49325018"
---
# <a name="set-a-watch-on-variables-using-the-watch-and-quickwatch-windows-in-visual-studio"></a>Visual Studio에서 조사식 및 간략 한 조사식 창을 사용 하 여 변수에 대 한 조사식 설정

디버그 하는 동안 사용할 수는 **조사식** 하 고 **간략 한 조사식** 변수 및 식을 조사 하려면 windows.  차이점은 **조사식** 창에는 여러 변수가 표시될 수 있는 반면 **간략한 조사식** 창에는 한 번에 하나의 변수가 표시된다는 것입니다.

Windows는 디버깅 세션 중만 사용할 수 있습니다. 열려는 합니다 **조사식** 창에서 선택 **디버그** > **Windows** > **조사식**를 선택한 다음 **조사식 1**, **조사식 2**하십시오 **조사식 3**, 또는 **조사식 4**. 열려는 합니다 **간략 한 조사식** 창 하거나 변수를 마우스 오른쪽 단추로 클릭 하 고 선택 **간략 한 조사식**를 선택 하거나 **디버그** > **간략 한 조사식** .

## <a name="observe-variables-with-the-watch-window"></a>조사식 창 사용 하 여 변수 관찰

사용 하 여 둘 이상의 변수를 확인할 수 있습니다 합니다 **조사식** 창입니다. 예를 들어 다음과 같은 코드를 가정해 봅니다.

```C++
int main()
{
    int a, b, c;
    a = 1;
    b = 2;
    c = 0;

    for (int i = 0; i < 10; i++)
    {
        a++;
        b *= 2;
        c = a + b;
    }

    return 0;
}

```

세 개의 변수를 값을 추가 합니다 **조사식** 같이 창:

1. 선택 된 `c = a + b;` 줄.

2. 중단점을 설정 (선택 하 여 **디버깅할** > **중단점 설정/해제** F9 키를 누르거나).

3. F5 키를 눌러 디버깅을 시작 합니다. 중단점에서 실행이 중지됩니다.

4. 엽니다는 **Watch** 창 (선택 하 여 **디버그** > **Windows** > **조사식**  >   **조사식 1**, Ctrl + Alt + w, 1 또는).

5. 빈 행을 선택 하 고 변수를 입력 `a`합니다. 그런 다음 변수에 대 한 동일한 작업을 수행할 `b` 고 `c`입니다.

   ![변수를 조사할](../debugger/media/watchvariables.png "WatchVariables")

6. 디버거를 진행 하는 데 필요한 대로 F11 키를 눌러 디버깅을 계속 합니다.

`for` 루프를 반복하면 변수 값이 변경됩니다.

네이티브 코드에서 프로그래밍 하는 경우 변수 이름 또는 변수 이름이 지정 된 식의 컨텍스트를 한 정해야 해야 경우가 있습니다. 컨텍스트는 변수가 있는 함수, 소스 파일 및 모듈입니다. 가 컨텍스트를 한 정해야 하는 경우에 컨텍스트 연산자 구문을 사용할 수 있습니다. 자세한 내용은 [컨텍스트 연산자 (c + +)](../debugger/context-operator-cpp.md)합니다.

## <a name="observe-expressions-with-the-watch-window"></a>조사식 창 사용 하 여 식 관찰

이제 대신 식을 사용 하 여 살펴보겠습니다. 디버거에서 인식할 수 있는 올바른 모든 식을 추가할 수 있습니다.

예를 들어, 이전 섹션에 나열 된 코드가 있는 경우이 식을 사용 하 여 세 가지 값의 평균을 가져올 수 있습니다.

![조사식](../debugger/media/watchexpression.png "WatchExpression")

식을 계산 하는 것에 대 한 규칙을 **조사식** 창은 일반적으로 코딩 언어에서 식을 계산 하는 것에 대 한 규칙과 동일 합니다. 식에 구문 오류가 있으면 코드 편집기에 표시 되는 동일한 컴파일러 오류를 예상 합니다. 예를 들면 다음과 같습니다.

![식 오류를 시청](../debugger/media/watchexpressionerror.png "WatchExpressionError")

## <a name="bkmk_refreshWatch"></a> 만료 된 조사식 값 새로 고침

식을 계산할 때 새로 고침 아이콘 (원형 화살표) 표시 될 수 있습니다 합니다 **조사식** 창입니다. 속성을 확인 하지 않도록 설정한 경우 (선택 하 여 **도구가** > **옵션** > **디버깅**  >   **일반**를 선택 취소 한 다음 **속성 확인 및 기타 암시적 함수 호출**), 다음 코드를 작성 및:

```csharp
static void Main(string[] args)
{
    List<string> list = new List<string>();
    list.Add("hello");
    list.Add("goodbye");
}

```

에 대 한 조사식을 설정 하면 다음 이미지와 같이 표시 되어야 합니다 `Count` 목록의 속성:

![RefreshWatch](../debugger/media/refreshwatch.png "RefreshWatch")

앞의 그림에서는 오류 또는 오래 된 값을 보여 줍니다. 아이콘을 선택 하 여 값 새로 고침 일반적으로 되지만 일부 경우에서 수도 있습니다를 새로 고칩니다. 먼저 값 계산 되지 않은 이유는 무엇 인지 알고 있어야 합니다.

도구 설명이 아이콘을 가리키는 경우 식은 평가 되지 않은 이유는 무엇에 대 한 정보를 제공 합니다. 서로 화살표가 나타나면 다음 이유 중 하나에 대 한 식이 계산 되지 않았습니다.

- 식 계산 중에 오류가 발생했습니다. 예를 들어 시간 초과가 발생했거나 변수가 범위를 벗어났습니다.

- 식에 응용 프로그램에서 부작용을 트리거할 수 있는 함수 호출 (참조를 [부작용 및 식](#bkmk_sideEffects) 섹션).

- 자동 속성 평가 하지 않도록 설정한 및 디버거에서 암시적 함수 호출 (선택 하 여 **도구가** > **옵션** > **디버깅**  >  **일반**을 선택 취소 한 다음 **속성 확인 및 기타 암시적 함수 호출**). 식은 자동으로 다음 평가할 수 없습니다.

값을 새로 고치려면 새로 고침 아이콘을 선택 하거나 스페이스바를 누릅니다. 디버거가 식을 다시 계산합니다. 새로 고침 아이콘 속성 및 기타 암시적 함수 호출의 자동 확인이 해제 되었기 때문에 나타날 수 있습니다. 이 경우 디버거에서 식을 평가할 수 있습니다.

아이콘에는 실 모양과 비슷한 두 물결선이 있는 원 나타날 수 있습니다. 이 아이콘은 디버거 잠재적 크로스 스레드 종속성으로 인해 식이 계산 되지 않고 의미 합니다. 즉, 코드를 확인할 때 응용 프로그램의 다른 스레드를 임시로 실행해야 함을 의미합니다. 중단 모드에서는 일반적으로 응용 프로그램의 모든 스레드가 중지됩니다. 다른 스레드를 임시로 실행할 수 있게 하면 프로그램 상태에 예기치 않은 영향이 있을 수 있으며 디버거가 중단점 및 해당 스레드에서 발생한 예외와 같은 이벤트를 무시하게 됩니다.

## <a name="bkmk_sideEffects"></a> 의도 및 식

일부 경우에는 식을 계산하면 변수 값이 바뀌거나 프로그램 상태에 영향이 미칠 수 있습니다. 예를 들어 다음 식을 계산하면 `var1`의 값이 변경됩니다.

```csharp
var1 = var2
```

이 코드에서 발생할 수 있습니다는 [부작용](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\))합니다. 부작용은 프로그램의 작동 방식을 변경하여 디버깅을 더 어렵게 만들 수 있습니다.

의도 하지 않은 알려진 식은 처음 입력할 때이 한 번만 평가 됩니다. 추가 계산은 수행 되지 않습니다. 수동으로 값 옆에 표시 되는 업데이트 아이콘을 선택 하 여이 동작을 재정의할 수 있습니다.

모든 부작용을 방지 하는 한 가지 방법은 자동 함수 계산을 해제 하는 (선택 하 여 **도구가** > **옵션** > **디버깅**  >  **일반적인**를 선택 취소 한 다음 **속성 확인 및 기타 암시적 함수 호출**).

암시적 함수 호출이나 속성의 계산을 해제한 경우 **ac** 형식 한정자를 사용하여 계산을 수행하게 할 수 있습니다(C#에만 해당). 참조 [형식 지정자에서 C#](../debugger/format-specifiers-in-csharp.md)합니다.

## <a name="bkmk_objectIds"></a> 조사식 창 (C# 및 Visual Basic)에서 개체 Id를 사용 합니다.

경우에 따라 특정 개체의 동작을 관찰 해야 합니다. 예를 들어, 다음 해당 변수 범위를 벗어난 후 지역 변수에 의해 참조 된 개체를 추적 하는 것이 좋습니다. C# 및 Visual Basic에서 참조 형식의 특정 인스턴스에 대 한 개체 Id를 만들고를 사용 하 여 **조사식** 창 및 중단점 조건에서. 개체 ID는 CLR(공용 언어 런타임) 디버깅 서비스에 의해 생성되고 개체와 연결됩니다.

> [!NOTE]
> 개체 Id는 가비지 수집 되지 않도록에서 개체를 방해 하지는 약한 참조를 만듭니다. 현재 디버깅 세션에 대해서만 유효합니다.

다음 코드는 한 가지 방법은 만듭니다는 `Person` 내용을 확인 하려면 로컬 변수를 사용 하 여는 `Person`의 이름은 다른 메서드에서:

```csharp
class Person
{
    public Person(string name)
    {
        Name = name;
    }
    public string Name { get; set; }
}

public class Program
{
    static List<Person> _people = new List<Person>();
    public static void Main(string[] args)
    {
        MakePerson();
        DoSomething();
    }

    private static void MakePerson()
    {
        var p = new Person("Bob");
        _people.Add(p);
    }

    private static void DoSomething()
    {
        // more processing
         Console.WriteLine("done");
    }
}

```

`Person` 조사식 **창에서 해당** 개체에 대한 참조를 다음과 같이 추가할 수 있습니다.

1. 개체를 만든 발생 하는 코드 줄을 선택 합니다.

2. 중단점을 설정 (선택 하 여 **디버깅할** > **중단점 설정/해제** F9 키를 누르거나).

3. 디버깅을 시작합니다.

4. 실행이 중단점에서 중지 되 면 엽니다는 **지역** 창 (선택 하 여 **디버그** > **Windows** > **지역**), 변수를 마우스 오른쪽 단추로 **개체 ID 만들기**합니다.

   달러 기호 표시 됩니다 (**$**) 더하기 숫자가 합니다 **지역** 창이 되 고 개체 id입니다.

   > [!NOTE]
   > 개체의 속성을 표시 하려는 경우 `Person.Name`를 선택 하 여 속성 평가 사용 해야 합니다 **도구** > **옵션**  >   **디버깅** > **일반**, 설정한 **속성 확인 및 기타 암시적 함수 호출**합니다.

5. 개체의 ID를 추가 합니다 **Watch** 달러 기호 및 번호를 마우스 오른쪽 단추로 클릭 한 다음 선택 하 여 창 **조사식 추가**합니다.

6. 개체의 동작을 관찰 하려는 중단점을 설정 합니다.  위의 코드에서 하는 것에 `DoSomething()` 메서드.

7. 디버깅을 계속합니다. 실행에서 중지 되는 경우는 `DoSomething()` 메서드를 **조사식** 창에 표시 됩니다는 `Person` 개체.

## <a name="use-registers-in-the-watch-window-c-only"></a>조사식 창 (c + + 전용)에서 레지스터 사용

등록 이름 및 변수 이름을 사용 하 여 추가할 수 있습니다  **$ \<등록&nbsp;이름 >** 하거나  **@ \<등록&nbsp;이름 >** 네이티브 코드 디버깅 중입니다. 자세한 내용은 [Pseudovariables](../debugger/pseudovariables.md)를 참조하세요.

## <a name="dynamic-view-and-the-watch-window"></a>동적 뷰 및 조사식 창

일부 스크립팅 언어 (예: JavaScript 또는 Python)를 사용 하 여 동적 또는 [덕 형식 지정](https://en.wikipedia.org/wiki/Duck_typing),.NET 언어 (4.0 이상 버전) 때문에 일반 디버깅 창을 사용 하 여 관찰 하기 어려운 개체를 지원 하 고 있습니다 런타임 속성 및 표시할 수 없는 메서드가 있을 수 있습니다.

합니다 **조사식** 창에는 동적 개체를 구현 하는 형식에서 생성 된 표시 될 수는 <xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스입니다. 이 개체가 표시 되 면 디버거는 특수 한을 추가 하는 **동적 뷰** 열면 개체 이름의 자식 노드를 **자동** 창 (선택 하 여 **디버그**  >  **Windows** > **자동**). 이 노드 동적 개체의 동적 멤버가 표시 되지만 멤버 값의 편집을 허용 하지 않습니다.

새 조사식을 삽입할 변수는 개체를 동적 개체:

1. 자식을 마우스 오른쪽 단추로 클릭 한 **동적 뷰**합니다.
2. 선택할 **조사식 추가**합니다. 그런 다음 `object.name` 가 `((dynamic) object).name`합니다.

**동적 뷰** 의 멤버 평가에 부작용이 있을 수 있습니다. 부작용의 설명에 대 한 참조를 [부작용 및 식](#bkmk_sideEffects) 섹션입니다. C# 디버거 하지 자동으로 다시 평가에 표시 된 값을 **동적 뷰** 코드의 새 줄으로 진행 하는 경우. Visual Basic의 경우 **동적 뷰** 를 통해 추가된 식이 자동으로 새로 고쳐집니다.

새로 고치는 방법에 대 한 지침은 **동적 뷰** 값을 참조 합니다 [만료 된 새로 고침 조사식 값](#bkmk_refreshWatch) 섹션입니다.

표시 하려는 경우는 **동적 뷰** 개체에 대해 사용할 수 있습니다 합니다 **동적** 형식 지정자에는 **조사식** 창:

- C#: `ObjectName, dynamic`
- Visual Basic: `$dynamic, ObjectName`

**동적 뷰** 는 COM 개체에 대한 디버깅 환경도 향상시킵니다. 디버거에 래핑된 COM 개체를 가져옵니다 하는 경우 **System.__ComObject**에서 추가 **동적 뷰** 개체에 대 한 노드.

## <a name="observe-a-single-variable-or-expression-with-quickwatch"></a>단일 변수 또는 간략 한 조사식을 사용 하 여 식 관찰

**간략한 조사식** 창을 사용하여 단일 변수를 관찰할 수 있습니다. 예를 들어 다음과 같은 코드를 가정해 봅니다.

```csharp
static void Main(string[] args)
{
    int a, b;
    a = 1;
    b = 2;
    for (int i = 0; i < 10; i++)
    {
        a = a + b;
    }
}
```

변수를 확인할 수 있습니다 합니다 **간략 한 조사식** 같이 창:

1. `a = a + b;` 줄에 중단점을 설정합니다.

2. 디버깅을 시작합니다. 중단점에서 실행이 중지됩니다.

3. 변수 선택 `a`합니다.

4. 선택 하거나 **디버깅할** > **간략 한 조사식** 누르거나 **shift+f9**합니다. 합니다 **간략 한 조사식** 창이 나타납니다. 에 **값** 상자는 `a` 변수 값이 1 인 표시 됩니다.

   ![간략 한 조사식 변수](../debugger/media/quickwatchvariable.png "QuickWatchVariable")

   변수를 사용 하 여 식을 평가 하는 식을 입력와 같은 `a + b` 에 **식** 상자 하 고 클릭 **다시 평가**합니다.

   ![조사식](../debugger/media/quickwatchexpression.png "QuickWatchExpression")

   변수 또는 식을 추가 하는 **조사식** 창에서 **간략 한 조사식**, 선택 **조사식 추가**합니다.

   > [!NOTE]
   > 합니다 **간략 한 조사식** 창은 모달 대화 상자 창 이므로 열려으로 디버깅을 계속할 수 없습니다.

5. **간략한 조사식** 창을 닫습니다. 이제 **조사식** 창을 닫습니다.

## <a name="see-also"></a>참고자료

[디버거 창](../debugger/debugger-windows.md)
