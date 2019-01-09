---
title: 'Ijsdebugdatatarget:: Readbstr 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.ReadBSTR
apilocation:
- jscript9diag.dll
ms.assetid: 4b571db7-04b9-42a0-9a3e-310ac9d0e659
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: afd216c869cd88a643f68f0abd1fc095a675e24b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095799"
---
# <a name="ijsdebugdatatargetreadbstr-method"></a>IJsDebugDataTarget::ReadBSTR 메서드
디버그 대상에서 읽히는 BSTR을 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ReadBSTR(  
   UINT64 address,  
   BSTR *pString  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] 읽을 주소입니다.  
  
 `pString`  
 [out] BSTR은 디버그 대상에서 읽습니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 주소가 올바르지 않으면 E_JsDEBUG_INVALID_MEMORY_ADDRESS를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)