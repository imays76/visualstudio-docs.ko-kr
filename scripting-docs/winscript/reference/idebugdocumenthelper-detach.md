---
title: IDebugDocumentHelper::Detach | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.Detach
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::Detach
ms.assetid: 820b9a8c-9a88-479a-b095-daea99394f9c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd86e1860cf4bd22a71b6f728ca36dbd3b7414a4
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089494"
---
# <a name="idebugdocumenthelperdetach"></a>IDebugDocumentHelper::Detach
문서 트리에서이 문서를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Detach();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수 없이 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 문서 트리에서이 문서를 제거합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Idebugdocumenthelper:: Attach](../../winscript/reference/idebugdocumenthelper-attach.md)   
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)