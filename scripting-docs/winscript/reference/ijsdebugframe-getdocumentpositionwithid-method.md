---
title: 'Ijsdebugframe:: Getdocumentpositionwithid 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetDocumentPositionWithId
apilocation:
- jscript9diag.dll
ms.assetid: 48f8eb26-8ae4-4d5c-bd94-796023b03bcb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c37f31ca6b75ca826dbdab93847a1e70ff054c1
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090014"
---
# <a name="ijsdebugframegetdocumentpositionwithid-method"></a>IJsDebugFrame::GetDocumentPositionWithId 메서드
사용자 수준 문서 내에서이 스택 프레임의 현재 위치를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetDocumentPositionWithId(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDocumentId`  
 [out] 원본 문서 (IDebugDocumentText에 대 한 포인터)에 대 한 고유 ID입니다.  
  
 `pCharacterOffset`  
 [out] 스크립트의 시작 부분에서 0부터 시작 문자 오프셋입니다.  
  
 `pStatementCharCount`  
 [out] 시작 하는 현재 문의 길이 * pCharacterOffset 문자입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)