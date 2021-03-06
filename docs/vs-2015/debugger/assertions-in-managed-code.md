---
title: 관리 코드에 어설션 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], assertions in managed code
- Trace.Assert method
- debugging managed code, assertions
- Debug.Assert method
- Debug.Listeners property
- assertions, side effects
- Trace.Listeners property
- assertions, managed code
ms.assetid: 70ab2522-6486-4076-a1a9-e0f11cd0f3a1
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c47b2b05ab358826d594d0c6ef29c1b50e0a529f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51806544"
---
# <a name="assertions-in-managed-code"></a>관리 코드에 어설션 사용
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

어설션 또는 `Assert` 문은 `Assert` 문에 대한 인수로 지정하는 조건을 테스트합니다. 조건이 true로 평가되면 동작이 발생하지 않고, 조건이 false로 평가되면 어설션이 실패합니다. 디버그 빌드로 실행 중인 경우 프로그램 중단 모드가 시작됩니다.  
  
##  <a name="BKMK_In_this_topic"></a> 항목 내용  
 [System.Diagnostics Namespace의 assert](#BKMK_Asserts_in_the_System_Diagnostics_Namespace)  
  
 [Debug.Assert 메서드](#BKMK_The_Debug_Assert_method)  
  
 [Debug.Assert의 파생 작업](#BKMK_Side_effects_of_Debug_Assert)  
  
 [Trace 및 Debug 요구 사항](#BKMK_Trace_and_Debug_Requirements)  
  
 [Assert 인수](#BKMK_Assert_arguments)  
  
 [Assert 동작 사용자 지정](#BKMK_Customizing_Assert_behavior)  
  
 [구성 파일에서 어설션 설정](#BKMK_Setting_assertions_in_configuration_files)  
  
##  <a name="BKMK_Asserts_in_the_System_Diagnostics_Namespace"></a> System.Diagnostics Namespace의 assert  
 Visual Basic 및 Visual C#에서는 `Assert` 네임스페이스에 있는 <xref:System.Diagnostics.Debug> 또는 <xref:System.Diagnostics.Trace>에서 <xref:System.Diagnostics> 메서드를 사용할 수 있습니다. <xref:System.Diagnostics.Debug> 클래스 메서드는 프로그램의 릴리스 버전에 포함되지 않으므로 릴리스 코드의 크기를 증가시키거나 속도를 떨어뜨리지 않습니다.  
  
 C++는 <xref:System.Diagnostics.Debug> 클래스 메서드를 지원하지 않습니다. 사용 하 여 동일한 효과 얻을 수 있습니다 합니다 <xref:System.Diagnostics.Trace> 와 같은 클래스에 조건부 컴파일을 `#ifdef DEBUG`... `#endif`.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_The_Debug_Assert_method"></a> Debug.Assert 메서드  
 코드가 정확한 경우 true로 유지되어야 하는 조건을 테스트하려면 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 메서드를 사용합니다. 예를 들어 정수 나누기 함수를 작성한 경우, 수학의 규칙에 따라 0으로는 나눌 수 없습니다. 다음과 같이 어설션을 사용하여 이를 테스트할 수 있습니다.  
  
```vb  
Function IntegerDivide(ByVal dividend As Integer, ByVal divisor As Integer) As Integer  
    Debug.Assert(divisor <> 0)  
    Return CInt(dividend / divisor)  
End Function  
```  
  
```csharp  
int IntegerDivide ( int dividend , int divisor )  
    { Debug.Assert ( divisor != 0 );  
        return ( dividend / divisor ); }  
```  
  
 디버거에서 이 코드를 실행하면 어설션 문이 평가되지만, 릴리스 버전에서는 비교가 실행되지 않으므로 추가 오버헤드가 없습니다.  
  
 또는 다음과 같은 예도 있습니다. 다음과 같이 당좌 예금 계좌를 구현하는 클래스가 있다고 가정합니다.  
  
```vb  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Debug.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Debug.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 계좌에서 돈을 인출하기 전에 인출하려는 금액 이상의 잔액이 있는지 확인해야 합니다. 다음과 같은 어설션을 작성하여 잔액을 확인할 수 있습니다.  
  
```vb  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Trace.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Trace.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 작성한 코드로 릴리스 버전을 만들면 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 메서드에 대한 호출이 사라집니다. 즉, 릴리스 버전에서는 잔액을 확인하는 호출이 사라집니다. 이 문제를 해결하려면 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 대신 릴리스 버전에서 사라지지 않는 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>를 사용해야 합니다.  
  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 호출과 달리 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 호출은 릴리스 버전에 오버헤드를 추가합니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Side_effects_of_Debug_Assert"></a> Debug.Assert의 파생 작업  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>를 사용할 때는 `Assert`가 제거되어도 `Assert` 내의 코드에 의해 프로그램의 결과가 변경되지 않도록 해야 합니다. 프로그램 결과가 변경되면 릴리스 버전의 프로그램에만 나타나는 버그가 발생할 수 있습니다. 특히 다음 예와 같이 함수 또는 프로시저 호출이 포함된 Assert를 사용할 경우에 주의해야 합니다.  
  
```vb  
' unsafe code  
Debug.Assert (meas(i) <> 0 )  
```  
  
```csharp  
// unsafe code  
Debug.Assert (meas(i) != 0 );  
```  
  
 이러한 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>의 사용이 안전해 보일 수도 있지만 meas 함수가 호출될 때마다 카운터를 업데이트한다고 가정해 보십시오. 릴리스 버전을 빌드할 때 이 meas에 대한 호출이 제거되므로 카운터는 업데이트되지 않습니다. 이는 파생 작업이 있는 함수의 예입니다. 파생 작업이 있는 함수에 대한 호출을 제거하면 릴리스 버전에서만 나타나는 버그가 발생할 수 있습니다. 이러한 문제를 방지하려면 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 문에 함수 호출을 배치하는 대신 다음과 같이 임시 변수를 사용합니다.  
  
```vb  
temp = meas( i )  
Debug.Assert (temp <> 0)  
```  
  
```csharp  
temp = meas( i );  
Debug.Assert ( temp != 0 );  
```  
  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>를 사용하는 경우에도 `Assert` 문 내에 함수 호출을 배치하지 않으려고 할 수 있습니다. <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 문은 릴리스 빌드에서 제거되지 않기 때문에 이러한 호출이 위험하지는 않습니다. 그러나 습관적으로 이러한 구문을 사용하지 않는 경우 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>를 사용할 때 실수를 줄일 수 있습니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Trace_and_Debug_Requirements"></a> Trace 및 Debug 요구 사항  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 마법사를 사용하여 프로젝트를 만드는 경우 릴리스 구성과 디버그 구성 모두에서 기본적으로 TRACE 기호가 정의됩니다. 디버그 기호는 기본적으로 디버그 빌드에서만 정의됩니다.  
  
 그 밖의 경우에 <xref:System.Diagnostics.Trace> 메서드가 작동하려면 프로그램의 소스 파일 맨 위에 다음 중 하나가 있어야 합니다.  
  
- Visual Basic에서는 `#Const TRACE = True`  
  
- Visual C# 및 C++에서는 `#define TRACE`  
  
  또는 다음과 같은 TRACE 옵션을 사용하여 프로그램을 빌드해야 합니다.  
  
- Visual Basic에서는 `/d:TRACE=True`  
  
- Visual C# 및 C++에서는 `/d:TRACE`  
  
  C# 또는 Visual Basic 릴리스 빌드에서 Debug 메서드를 사용해야 하는 경우 릴리스 구성에서 디버그 기호를 정의해야 합니다.  
  
  C++는 <xref:System.Diagnostics.Debug> 클래스 메서드를 지원하지 않습니다. 사용 하 여 동일한 효과 얻을 수 있습니다 합니다 <xref:System.Diagnostics.Trace> 와 같은 클래스에 조건부 컴파일을 `#ifdef DEBUG`... `#endif`. 이러한 기호를 정의할 수 있습니다 합니다  **\<프로젝트 > 속성 페이지** 대화 상자. 자세한 내용은 [Visual Basic 디버그 구성에 대 한 프로젝트 설정 변경](../debugger/project-settings-for-a-visual-basic-debug-configuration.md) 또는 [C 또는 c + + 디버그 구성에 대 한 프로젝트 설정 변경](../debugger/project-settings-for-a-cpp-debug-configuration.md)합니다.  
  
##  <a name="BKMK_Assert_arguments"></a> Assert 인수  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>에는 세 가지 인수가 사용됩니다. 첫 번째 인수는 확인할 조건으로, 필수 인수입니다. 호출 하는 경우 <xref:System.Diagnostics.Trace.Assert%28System.Boolean%29?displayProperty=fullName> 또는 <xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName> 하나의 인수를 사용 합니다 `Assert` 메서드 조건을 확인 하 고, 결과가 false 인 경우에 호출 스택의 내용을 출력 합니다 **출력** 창. 다음 예제에서는 <xref:System.Diagnostics.Trace.Assert%28System.Boolean%29?displayProperty=fullName> 및 <xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName>를 보여 줍니다.  
  
```vb  
Debug.Assert(stacksize > 0)  
Trace.Assert(stacksize > 0)  
```  
  
```csharp  
Debug.Assert ( stacksize > 0 );  
Trace.Assert ( stacksize > 0 );   
```  
  
 두 번째 및 세 번째 인수는 선택적으로 지정되는 문자열입니다. 인수를 두 개나 세 개 사용하여 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 또는 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>를 호출하는 경우 첫 번째 인수는 조건입니다. 메서드는 조건을 확인하고 그 결과가 false인 경우 두 번째 문자열과 세 번째 문자열을 출력합니다. 다음 예제에서는 인수 두 개를 사용하는 <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName>를 보여 줍니다.  
  
```vb  
Debug.Assert(stacksize > 0, "Out of stack space")  
Trace.Assert(stacksize > 0, "Out of stack space")  
```  
  
```csharp  
Debug.Assert ( stacksize > 0, "Out of stack space" );  
Trace.Assert ( stacksize > 0, "Out of stack space" );  
```  
  
 다음 예제에서는 <xref:System.Diagnostics.Debug.Assert%2A> 및 <xref:System.Diagnostics.Trace.Assert%2A>를 보여 줍니다.  
  
```vb  
Debug.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:", "inctemp failed on third call" )  
```  
  
```csharp  
Debug.Assert ( stacksize > 100, "Out of stack space" , "Failed in inctemp" );  
Trace.Assert ( stacksize > 0, "Out of stack space", "Failed in inctemp" );   
```  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Customizing_Assert_behavior"></a> Assert 동작 사용자 지정  
 사용자 인터페이스 모드로 응용 프로그램을 실행 하는 경우는 `Assert` 메서드 표시 합니다 **어설션이 실패 한** 조건이 실패 하면 대화 상자. 어설션이 실패할 때 발생 하는 작업에 의해 제어 되는 <xref:System.Diagnostics.Debug.Listeners%2A> 또는 <xref:System.Diagnostics.Trace.Listeners%2A> 속성입니다.  
  
 <xref:System.Diagnostics.TraceListener> 개체를 `Listeners` 컬렉션에 추가하거나, <xref:System.Diagnostics.TraceListener>를 `Listeners` 컬렉션에서 제거하거나, 기존 <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName>의 `TraceListener` 메서드를 다르게 동작하도록 재정의하는 방법으로 출력 동작을 사용자 지정할 수 있습니다.  
  
 예를 들어 재정의할 수 있습니다 합니다 <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> 메서드를 표시 하는 대신 이벤트 로그를 씁니다 합니다 **어설션이 실패 한** 대화 상자.  
  
 이러한 방법으로 출력을 사용자 지정하려면 프로그램에 수신기가 있어야 하고 사용자가 <xref:System.Diagnostics.TraceListener>에서 상속하여 <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> 메서드를 재정의해야 합니다.  
  
 자세한 내용은 [추적 수신기](http://msdn.microsoft.com/library/444b0d33-67ea-4c36-9e94-79c50f839025)합니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Setting_assertions_in_configuration_files"></a> 구성 파일에서 어설션 설정  
 코드뿐만 아니라 프로그램 구성 파일에서도 어설션을 설정할 수 있습니다. 자세한 내용은 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 또는 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>   
 [디버거 보안](../debugger/debugger-security.md)   
 [응용 프로그램 추적 및 조율](http://msdn.microsoft.com/library/773b6fc4-9013-4322-b728-5dec7a72e743)   
 [방법: 추적 및 디버그를 사용한 조건부 컴파일](http://msdn.microsoft.com/library/56d051c3-012c-42c1-9a58-7270edc624aa)   
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [관리 코드 디버그](../debugger/debugging-managed-code.md)



