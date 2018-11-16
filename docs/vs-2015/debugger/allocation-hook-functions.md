---
title: 할당 후크 함수 | Microsoft Docs
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
- memory allocation, logging allocation information
- insufficient memory
- debugging [C++], hook functions
- _CrtSetAllocHook function
- allocation hooks
- hooks, allocation
ms.assetid: 6bfbdb65-8cb1-4c21-8c45-7194a2b77c1e
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d201f22d461a04890899ac1cebc177cb1521555
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51743344"
---
# <a name="allocation-hook-functions"></a>할당 후크 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

할당 후크 함수를 사용 하 여 설치할 [_CrtSetAllocHook](http://msdn.microsoft.com/library/405df37b-2fd1-42c8-83bc-90887f17f29d), 메모리 할당, 다시 할당 하거나 해제할 때마다 호출 됩니다. 이러한 후크 형식은 여러 가지 목적으로 사용할 수 있습니다. 예를 들어, 메모리가 부족할 때 응용 프로그램이 이 상황을 어떻게 처리하는지 테스트하거나 할당 패턴을 검사하거나 나중에 분석하기 위해 할당 정보를 기록하는 데 사용할 수 있습니다.  
  
> [!NOTE]
>  에 설명 된 할당 후크 함수를 사용 하는 작업에서 C 런타임 라이브러리 함수를 사용 하는 방법에 대 한 제한에 유의 [할당 후크 및 C 런타임 메모리 할당](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)합니다.  
  
 할당 후크 함수에는 다음과 같은 프로토타입이 있어야 합니다.  
  
```  
int YourAllocHook(int nAllocType, void *pvData,  
        size_t nSize, int nBlockUse, long lRequest,  
        const unsigned char * szFileName, int nLine )  
```  
  
 에 전달 하는 포인터 [_CrtSetAllocHook](http://msdn.microsoft.com/library/405df37b-2fd1-42c8-83bc-90887f17f29d) 유형의 **_CRT_ALLOC_HOOK**CRTDBG에 정의 된 대로 합니다. H:  
  
```  
typedef int (__cdecl * _CRT_ALLOC_HOOK)  
    (int, void *, size_t, int, long, const unsigned char *, int);  
```  
  
 런타임 라이브러리가 후크를 호출 하는 경우는 *nAllocType* 인수는 할당 나타냅니다 수행할 작업이 (**_HOOK_ALLOC**를 **_HOOK_REALLOC**, 또는 **_HOOK_FREE**). 해제하거나 다시 할당할 경우에는 해제할 블록의 사용자 항목에 대한 포인터가 `pvData`에 포함됩니다. 그러나, 할당할 경우에는 할당이 아직 발생하지 않았기 때문에 이 포인터가 null입니다. 해당 할당 크기, 블록 형식, 연결되어 있는 다음 요청 번호, 할당이 이루어진 파일 이름과 줄 번호에 대한 포인터(있을 경우) 등은 나머지 인수에 포함되어 있습니다. 어떤 분석을 수행 하는 후크 함수를 사용 하는 다른 작업을 반환 해야 하거나 **TRUE**, 할당 작업을 계속할 수 있음을 나타내는 또는 **FALSE**나타내는 하는 작업은 실패 합니다. 간단한이 형식의 후크가 있습니다 지금 할당 된 메모리 양을 확인 하 고 반환 **FALSE** 크기가 작은 한계를 초과 하는 경우. 그러면 사용할 수 있는 메모리가 부족한 경우에만 주로 발생하는 할당 오류가 응용 프로그램에 발생합니다. 좀 더 복잡한 후크는 할당 패턴을 추적하거나 메모리 사용을 분석하거나 특정 상황이 발생하는 때를 보고할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [할당 후크 및 C 런타임 메모리 할당](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)   
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 샘플](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)



