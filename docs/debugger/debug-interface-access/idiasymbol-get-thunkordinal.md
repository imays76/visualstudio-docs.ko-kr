---
title: 'Idiasymbol:: Get_thunkordinal | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b13669c7a93141f3b54c15a20a5faee43d5a8747
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53953211"
---
# <a name="idiasymbolgetthunkordinal"></a>IDiaSymbol::get_thunkOrdinal
함수의 썽크 형식을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_thunkOrdinal (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 값을 반환 합니다 [THUNK_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md) 함수의 썽크 형식을 지정 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>주의  
 이 속성은 유효한 경우에만 기호는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 의 값 `SymTagThunk`합니다.  
  
 "썽크"은 (플랫 주소 공간이 라고도 함)는 32 비트 메모리 주소 공간 및 16 비트 주소 공간 (분할 된 주소 공간 이라고 함) 간에 변환 되는 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [THUNK_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)