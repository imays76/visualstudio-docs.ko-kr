---
title: JsDebugReadMemoryFlags 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JsDebugReadMemoryFlags
apilocation:
- jscript9diag.dll
ms.assetid: 0d98d154-9cb1-49de-b2df-a2d029d343b7
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bef1f16ebcf678452f2fe4b0df3ade6350120f05
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094031"
---
# <a name="jsdebugreadmemoryflags-enumeration"></a>JsDebugReadMemoryFlags 열거형
메모리를 읽을 때의 동작을 지정하는 플래그입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
enum JsDebugReadMemoryFlags{   None = 0,   JsDebugAllowPartialRead= 0x1} JsDebugReadMemoryFlags;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`JsDebugAllowPartialRead`|호출자에 게는 읽기 작업이 성공 메모리의 일부를 읽을 경우 성공 하기를 원한다는 것을 나타냅니다. 이 값으로 설정 하는 경우 E_JsDEBUG_INVALID_MEMORY_ADDRESS 오류만 발생 '주소'에 유효 하지 않은 경우. 이 플래그 지우기 인 경우 요청된 된 메모리의 일부를 읽을 수 없습니다 경우 E_JsDEBUG_INVALID_MEMORY_ADDRESS 오류가 발생 합니다.|  
|`None`|호출자가 ReadMemory에 대 한 기본 동작을 원한다는 것을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)