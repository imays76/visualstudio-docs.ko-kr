---
title: IDebugDocumentInfo::GetName | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentInfo.GetName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentInfo::GetName
ms.assetid: c25d73da-99b6-4c9f-82af-182b4853f81c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f3ecde4fbde1a265596a01d7f0f953763363e797
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097697"
---
# <a name="idebugdocumentinfogetname"></a>IDebugDocumentInfo::GetName
지정 된 문서 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetName(  
   DOCUMENTNAMETYPE  dnt,  
   BSTR*             pbstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dnt`  
 [in] 반환할 문서 이름의 형식입니다.  
  
 `pbstrName`  
 [out] 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|지정한 문서 이름 알 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정 된 문서 이름을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentInfo 인터페이스](../../winscript/reference/idebugdocumentinfo-interface.md)   
 [DOCUMENTNAMETYPE 열거형](../../winscript/reference/documentnametype-enumeration.md)