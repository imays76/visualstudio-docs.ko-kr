---
title: 'Idebugdocumenthelper:: Init | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.Init
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::Init
ms.assetid: 1dd5a01f-0779-4109-8c6c-f16f5a3835bf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4bcb64b7bbb1c61e7f031d872f7d1440fd17833
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086634"
---
# <a name="idebugdocumenthelperinit"></a>IDebugDocumentHelper::Init
`Init` 메서드 이름과 초기 특성을 사용 하 여 디버그 문서 도우미를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Init(  
   IDebugApplication*  pda,  
   LPCOLESTR           pszShortName,  
   LPCOLESTR           pszLongName,  
   TEXT_DOC_ATTR       docAttr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pda`  
 [in] 이 문서와 연결 된 디버그 응용 프로그램입니다.  
  
 `pszShortName`  
 [in] 문서의 짧은 이름을 포함 하는 null 종료 문자열입니다.  
  
 `pszLongName`  
 [in] 문서의 긴 이름을 포함 하는 null 종료 문자열입니다.  
  
 `docAttr`  
 [in] 텍스트 문서 특성을 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드 이름과 초기 특성을 사용 하 여 디버그 문서 도우미를 초기화합니다.  
  
 이 문서까지 트리에 나타나지 `IDebugDocumentHelper::Attach` 라고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Idebugdocumenthelper:: Attach](../../winscript/reference/idebugdocumenthelper-attach.md)   
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [TEXT_DOC_ATTR 상수](../../winscript/reference/text-doc-attr-constants.md)