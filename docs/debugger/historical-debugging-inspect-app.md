---
title: 기록 디버깅을 사용 하 여 앱 검사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 629b5d93-39b2-430a-b8ba-d2a47fdf2584
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2309a3213344607fa0f5b2f626fc67af2eff8f79
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542340"
---
# <a name="inspect-your-app-with-intellitrace-historical-debugging-in-visual-studio"></a>IntelliTrace 기록 디버깅 Visual Studio에서 사용 하 여 앱 검사
사용할 수 있습니다 [기록 디버깅](../debugger/historical-debugging.md) 뒤로 이동 하 고 응용 프로그램의 실행을 통해 전달 및 해당 상태를 검사 합니다.  
  
Visual Studio Enterprise edition 에서만 Professional 또는 Community edition 아님 IntelliTrace를 사용할 수 있습니다.  
  
## <a name="navigate-your-code-with-historical-debugging"></a>기록 디버깅을 사용 하 여 코드 탐색  
 버그가 있는 간단한 프로그램으로 시작 해 보겠습니다. C# 콘솔 응용 프로그램에서 다음 코드를 추가합니다.  
  
```csharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    int resultInt = AddAll(testInt);  
    Console.WriteLine(resultInt);  
}  
private static int AddAll(int j)  
{  
    for (int i = 0; i < 20; i++)  
    {  
        j = AddInt(j);  
    }  
    return j;  
}  
  
private static int AddInt(int add)  
{  
    if (add == 10)  
    {  
        return add += 25;  
    }  
    return ++add;  
}  
```  
  
 가정 하겠습니다의 예상 값 `resultInt` 호출한 후 `AddAll()` 는 20 개입니다 (증분 한 결과 `testInt` 20 배). (버그를 볼 수 없습니다는 또한 가정 하겠습니다 `AddInt()`). 하지만 결과 실제로 44입니다. `AddAll()`을 단계적으로 10회 실행하지 않고도 버그를 찾으려면 어떻게 할까요? 기록 디버깅을 사용 했습니다 빠르고 쉽게 버그를 찾을 수 있습니다. 방법은 다음과 같습니다.  
  
1.  **도구 > 옵션 > IntelliTrace > 일반**IntelliTrace 활성화 되어 있는지 확인 하 고 선택 **IntelliTrace 이벤트 및 호출 정보**합니다. 이 옵션을 선택하지 않으면 탐색 여백(아래 설명)을 볼 수 없습니다.  
  
2.  `Console.WriteLine(resultInt);` 줄에 중단점을 설정합니다.  
  
3.  디버깅을 시작합니다. 코드가 중단점까지 실행됩니다. 에 **지역** 창에서 볼 수 있습니다 값 `resultInt` 44입니다.  
  
4.  엽니다는 **진단 도구** 창 (**디버그 > 진단 도구 표시**). 코드 창이 다음과 같이 나타납니다.  
  
     ![중단점에서 코드 창](../debugger/media/historicaldebuggingbreakpoint.png "HistoricalDebuggingBreakpoint")  
  
5.  중단점 바로 위 왼쪽 여백 옆에 이중 화살표가 표시됩니다. 이 영역은 탐색 여백 이라고 하며 기록 디버깅을 위해 사용 됩니다. 화살표를 클릭합니다.  
  
     코드 창에서 위 코드 줄(`int resultInt = AddIterative(testInt);`)에 분홍색이 지정된 것을 확인할 수 있습니다. 창 위에 기록 디버깅에서 작업 하는 메시지가 표시 됩니다.  
  
     이제 코드 창의 모양은 다음과 같습니다.  
  
     ![기록 디버깅 모드에 있는 코드 창을](../debugger/media/historicaldebuggingback.png "HistoricalDebuggingBack")  
  
6.  이제 한 단계씩 실행할 수는 `AddAll()` 메서드 (**F11**, 또는 **단계씩** 탐색 여백에 있는 단추입니다. 앞으로 가기 (**F10**, 또는 **다음 호출로 이동** 탐색 여백의 합니다. 분홍색 줄이 `j = AddInt(j);` 줄에 표시됩니다. **F10** 이 경우 코드의 다음 줄으로 진행 하지 않습니다. 대신, 다음 함수 호출로 이동합니다. 기록 디버깅은 여러 호출을 탐색하며 함수 호출이 포함되지 않은 코드 줄을 건너뜁니다.  
  
7.  이제 `AddInt()` 메서드를 한 단계씩 실행합니다. 이 코드의 버그가 즉시 표시됩니다.  

## <a name="next-steps"></a>다음 단계

이 절차는 방금 기록 디버깅으로 수행할 수 있는 작업의 극히.

- 디버깅 하는 동안 스냅숏을 보려면를 참조 하세요 [IntelliTrace를 사용 하 여 이전 앱 상태를 검사](../debugger/view-historical-application-state.md)합니다.
- 다양 한 설정 및 탐색 여백에 있는 여러 단추의 효과 대 한 자세한 내용을 참조 하세요 [IntelliTrace 기능](../debugger/intellitrace-features.md)합니다.