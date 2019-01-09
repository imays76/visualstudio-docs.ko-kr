---
title: IDebugApplication::FCanJitDebug | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.FCanJitDebug
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::FCanJitDebug
ms.assetid: d7ddac65-4864-411f-bf66-34a46c03f239
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6808c8bb7e27e7b416e79b2f23e323c3ae3a528f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095357"
---
# <a name="idebugapplicationfcanjitdebug"></a>IDebugApplication::FCanJitDebug
(JIT)-just-in-time 디버거에 등록 되어 있는지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
BOOL FCanJitDebug();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수 없이 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 반환 하는 경우 메서드가 성공 하면와 JIT 디버거 등록 `TRUE`합니다. 그 외의 경우 `FALSE`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 JIT 디버거 등록 되어 있는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)