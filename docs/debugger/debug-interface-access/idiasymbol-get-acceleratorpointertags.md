---
title: IDiaSymbol::get_acceleratorPointerTags | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e65def0ac8e94b2f113332981f57c051896f6bd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875461"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
C + + AMP 액셀러레이터 스텁 함수에 해당 하는 모든 가속기 포인터 태그 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cnt`  
 [in] 출력 배열의 크기 `pPointerTags`합니다.  
  
 `pcnt`  
 [out] C + + AMP 액셀러레이터 스텁 함수에서 가속기 포인터 태그의 수입니다.  
  
 `pPointerTags`  
 [out] `DWORD` 배열 포인터를 c + + AMP 액셀러레이터 스텁 함수에서 가속기 포인터 태그 값으로 채워집니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드가 호출 되는 `IDiaSymbol` c + + AMP 액셀러레이터 스텁 함수에 해당 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)