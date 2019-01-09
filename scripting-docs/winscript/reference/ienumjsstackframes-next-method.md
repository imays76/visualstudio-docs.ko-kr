---
title: 'Ienumjsstackframes:: Next 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumJsStackFrames.Next
apilocation:
- jscript9diag.dll
ms.assetid: efceb3a1-9239-4f55-9cbb-94670679988b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1838d6494311502faf99d86c80e0a74ded4c6e5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092406"
---
# <a name="ienumjsstackframesnext-method"></a>IEnumJsStackFrames::Next 메서드
지정 된 프레임 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Next(  
   ULONG cFrameCount,  
   JS_NATIVE_FRAME *pFrames,  
   ULONG *pcFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cFrameCount`  
 [in] 가져올 프레임의 수입니다.  
  
 `pFrames`  
 [out] 프레임을 저장 하는 배열입니다.  
  
 `pcFetched`  
 [out] 반환 된 프레임 수입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IEnumJsStackFrames 인터페이스](../../winscript/reference/ienumjsstackframes-interface.md)