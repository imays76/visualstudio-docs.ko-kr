---
title: 'Idiasymbol:: Get_offset | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_offset method
ms.assetid: 8292bb08-4dc8-4663-beb4-258f5d5a448d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1de1a7ed53c1f252958c70001b1609b82e715078
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556388"
---
# <a name="idiasymbolgetoffset"></a>IDiaSymbol::get_offset
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiasymbol:: Get_offset](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-offset)합니다.  
  
기호 위치 오프셋을 검색합니다. 사용 시기를 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 됩니다 `LocIsRegRel` 또는 `LocIsBitField`.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
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



