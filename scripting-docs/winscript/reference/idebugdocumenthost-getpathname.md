---
title: IDebugDocumentHost::GetPathName | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.GetPathName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::GetPathName
ms.assetid: 8abe2a86-e467-4ac9-8ccb-8761141bfa0d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c33844ade2367ffeb7690306a5febbabde2f016
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096033"
---
# <a name="idebugdocumenthostgetpathname"></a>IDebugDocumentHost::GetPathName
문서의 소스 파일의 전체 경로 및 파일 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrLongName`  
 [out] 긴 이름을 포함 하는 문자열입니다.  
  
 `pfIsOriginalFile`  
 [out] 플래그는 true 이면 `pbstrLongName` 그렇지 않으면 false 문서에 대 한 원본 파일을 가리킵니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|소스 파일이 없습니다를 만들거나 확인할 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 문서의 소스 파일의 전체 경로 및 파일 이름을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)