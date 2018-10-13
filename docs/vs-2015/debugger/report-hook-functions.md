---
title: 보고서 후크 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 557790edc774bab9db43830a4f5fc3e21cfc9758
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49279450"
---
# <a name="report-hook-functions"></a>보고서 후크 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

보고서 후크 함수를 사용 하 여 설치할 [_CrtSetReportHook](http://msdn.microsoft.com/library/1ae7c64f-8c84-4797-9574-b59f00f7a509), 때마다 호출 됩니다 [_CrtDbgReport](http://msdn.microsoft.com/library/6e581fb6-f7fb-4716-9432-f0145d639ecc) 디버그 보고서를 생성 합니다. 보고서 후크 함수를 사용하여 특정한 할당 형식에 맞게 보고서를 필터링할 수 있습니다. 보고서 후크 함수에는 다음과 같이 프로토타입이 있어야 합니다.  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 에 전달 하는 포인터 **_CrtSetReportHook** 유형의 **_CRT_REPORT_HOOK**CRTDBG에 정의 된 대로 합니다. H:  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 런타임 라이브러리에 후크 함수를 호출 하는 경우는 *nRptType* 보고서의 범주를 포함 하는 인수 (**_CRT_WARN**합니다 **_CRT_ERROR**, 또는 **_CRT _ASSERT**), *szMsg* 는 완전히 어셈블된 보고서 메시지 문자열에 대 한 포인터를 포함 하 고 *retVal* 지정 하는지 여부를 `_CrtDbgReport` 정상적인 실행을 계속할지 보고서 또는 디버거를 시작 합니다를 생성 합니다. (A *retVal* 값이 0 이면 계속 실행 하 고 값이 1 디버거를 시작 합니다.)  
  
 경우는 해당 메시지를 후크가 완전히 처리는 더 이상 보고 하지 않으려면 검사가 필요 하도록, 반환할 **TRUE**합니다. 반환 하는 경우 **FALSE**, `_CrtDbgReport` 보고서 메시지를 일반적으로 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 샘플](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)



