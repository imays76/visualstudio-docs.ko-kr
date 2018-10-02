---
title: 포인터가 메모리 주소를 손상시키는지 어떻게 알 수 있습니까? | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
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
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c9d3a6c754aa200703c5f2a0ed2e458e08830a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47557326"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>포인터가 메모리 주소를 손상시키는지 어떻게 알 수 있습니까?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [어떻게 찾습니까 해야 하는 경우 내 포인터 손상 메모리 주소?](https://docs.microsoft.com/visualstudio/debugger/how-can-i-find-out-if-my-pointers-corrupt-a-memory-address-q)합니다.  
  
문제 설명  
 포인터 하나가 0x00408000 주소의 메모리를 손상시키고 있는 것 같습니다. 어떻게 알아 낼 수 있습니까?  
  
## <a name="solution"></a>솔루션  
  
#### <a name="check-for-heap-corruption"></a>힙 손상 확인  
  
-   대부분의 메모리 손상은 실제로 힙 손상으로 인해 발생합니다. 전역 플래그 유틸리티(gflags.exe) 또는 pageheap.exe를 사용해 보십시오. 참조 [ http://support.microsoft.com/default.aspx?scid=kb; en-우리; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470)합니다.  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>메모리 주소가 수정된 위치를 찾으려면  
  
1.  0x00408000에 데이터 중단점을 설정합니다. 참조 [(네이티브 c + + 전용) 데이터 변경 중단점 설정](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only)합니다.  
  
2.  중단점에 도달 하면 사용 된 **메모리** 메모리를 보려면 창 콘텐츠 0x00408000에서 시작 합니다. 자세한 내용은 [메모리 Windows](../debugger/memory-windows.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그 Faq](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)



