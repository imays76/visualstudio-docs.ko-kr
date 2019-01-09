---
title: IDebugProperty::SetValueAsString | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.SetValueAsString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::SetValueAsString
ms.assetid: cad8d7b2-19a5-4a29-9000-cafdecdc238b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b106b1e553d3600d51b8b0fc09a0f8ecd4256abd
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097619"
---
# <a name="idebugpropertysetvalueasstring"></a>IDebugProperty::SetValueAsString
지정된 된 문자열에서 속성의 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetValueAsString (  
   LPCOLESTR pszValue,  
   UINTnRadix,  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszValue`  
 [in] 설정할 값입니다.  
  
 `nRadix`  
 [in] 모든 숫자 정보를 해석 하는 데 사용할 기 수입니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)