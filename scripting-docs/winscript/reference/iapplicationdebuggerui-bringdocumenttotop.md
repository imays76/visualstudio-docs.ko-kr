---
title: IApplicationDebuggerUI::BringDocumentToTop | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebuggerUI.BringDocumentToTop
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebuggerUI::BringDocumentToTop
ms.assetid: ef5fe1e7-4381-4409-a0d7-58f993abe84e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c77c87011c539e02f92aa2aedfdcd7659466d37
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096254"
---
# <a name="iapplicationdebuggeruibringdocumenttotop"></a>IApplicationDebuggerUI::BringDocumentToTop
디버거에서 맨 위에 지정 된 디버그 문서가 포함 된 창 사용자 인터페이스를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT BringDocumentToTop(  
   IDebugDocumentText*  pddt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pddt`  
 [in] 문서 맨 위에 디버거 사용자 인터페이스를 디버그 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_INVALIDARG`|문서 알 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버거에서 맨 위에 지정 된 디버그 문서가 포함 된 창 사용자 인터페이스를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IApplicationDebuggerUI 인터페이스](../../winscript/reference/iapplicationdebuggerui-interface.md)