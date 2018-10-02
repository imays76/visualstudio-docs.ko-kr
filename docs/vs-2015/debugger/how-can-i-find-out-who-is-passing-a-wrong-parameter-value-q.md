---
title: 무엇이 잘못된 매개 변수 값을 전달하는지 어떻게 알 수 있습니까? | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.parameters
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1d7ae67e7ba09a25277afc55ef92da47a8e770d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549451"
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>무엇이 잘못된 매개 변수 값을 전달하는지 어떻게 알 수 있습니까?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [하는 방법을 알아 보기 무엇이 잘못 된 매개 변수 값을 전달?](https://docs.microsoft.com/visualstudio/debugger/how-can-i-find-out-who-is-passing-a-wrong-parameter-value-q)합니다.  
  
문제 설명  
 함수 하나에 잘못된 매개 변수 값이 전달되고 있습니다. 모든 위치에서 이 함수가 호출됩니다. 무엇이 잘못된 값을 전달하고 있는지 어떻게 알 수 있습니까?  
  
## <a name="solution"></a>솔루션  
  
#### <a name="to-resolve-this-problem"></a>이 문제를 해결하려면  
  
1.  함수 시작 부분에 위치 중단점을 설정합니다.  
  
2.  중단점을 마우스 오른쪽 단추로 클릭 **조건을**합니다.  
  
3.  에 **중단점 조건** 대화 상자를 클릭 합니다 **조건** 확인란 합니다. 참조 [중단점 고급](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)합니다.  
  
4.  텍스트 상자에 `Var==3` 같은 식을 입력합니다. 여기서 `Var`은 잘못된 값을 포함하는 매개 변수의 이름이고 `3`은 이 매개 변수에 전달된 잘못된 값입니다.  
  
5.  선택 된 **가 True** 라디오 단추를 클릭 하 고는 **확인** 단추.  
  
6.  이제 프로그램을 다시 실행합니다. `Var` 매개 변수의 값이 `3`인 경우 중단점은 함수의 시작 부분에서 프로그램을 중단하게 합니다.  
  
7.  호출 스택 창을 사용하여 호출하는 함수를 찾고 함수의 소스 코드를 탐색합니다. 자세한 내용은 [방법: 호출 스택 창을 사용 하 여](../debugger/how-to-use-the-call-stack-window.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그 Faq](../debugger/debugging-native-code-faqs.md)   
 [중단점](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)



