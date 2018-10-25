---
title: 'Idiasymbol:: Get_offset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_offset method
ms.assetid: 8292bb08-4dc8-4663-beb4-258f5d5a448d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0b2fa3ed234532ad3de02a31d4600f10f5375ad3
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49850076"
---
# <a name="idiasymbolgetoffset"></a>IDiaSymbol::get_offset
기호 위치 오프셋을 검색합니다. 사용 시기를 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 됩니다 `LocIsRegRel` 또는 `LocIsBitField`.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_offset (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 기호 위치의 바이트 오프셋을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 이전에 결정 하는 몇 가지 알려진된 지점에서 오프셋이입니다. 예를 들어, 오프셋을 `LocIsBitField` 위치 형식은 일반적으로 포함 하는 클래스의 시작 부분에서.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v7.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)