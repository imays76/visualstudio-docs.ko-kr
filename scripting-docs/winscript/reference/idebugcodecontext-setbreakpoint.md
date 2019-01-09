---
title: IDebugCodeContext::SetBreakPoint | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugCodeContext.SetBreakPoint
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugCodeContext::SetBreakPoint
ms.assetid: ecd42eae-66fa-40d3-9e47-08b826784108
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7f0199c111e620d9b1783ed8da7163d10f2e20b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095786"
---
# <a name="idebugcodecontextsetbreakpoint"></a>IDebugCodeContext::SetBreakPoint
설정 하거나이 코드 컨텍스트에 중단점을 지웁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetBreakPoint(  
   BREAKPOINT_STATE  bps  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bps`  
 [in] 이 코드 컨텍스트에 대 한 중단점 상태를 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드를 설정 하거나이 코드 컨텍스트에 중단점을 지웁니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCodeContext 인터페이스](../../winscript/reference/idebugcodecontext-interface.md)   
 [BREAKPOINT_STATE 열거형](../../winscript/reference/breakpoint-state-enumeration.md)