---
title: 'Idiaframedata:: Get_lengthsavedregisters | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_lengthSavedRegisters method
ms.assetid: dfda4e91-9bfa-4b9d-9133-b73015bfa4d5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7bb5fc5469aecdfbfee9a7f24586c384013f89f0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53912758"
---
# <a name="idiaframedatagetlengthsavedregisters"></a>IDiaFrameData::get_lengthSavedRegisters
스택에 저장 된 레지스터의 바이트 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_lengthSavedRegisters (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 저장 된 레지스터의 바이트 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>주의  
 이 메서드에서 반환 되는 값은 프로그램 문자열의 해석에 일반적으로 사용 됩니다 (참조를 [idiaframedata:: Get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md) 프로그램 문자열로의 정의 대 한 메서드).  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)