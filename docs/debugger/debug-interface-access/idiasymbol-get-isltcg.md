---
title: 'Idiasymbol:: Get_isltcg | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 33d3ea0720e7354cc50e77d555adc5af43ac9d96
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53831799"
---
# <a name="idiasymbolgetisltcg"></a>IDiaSymbol::get_isLTCG
지정 하는 플래그를 검색 하는지 여부를 [Compiland](../../debugger/debug-interface-access/compiland.md) 링커 스위치를 사용 하 여 연결 되었습니다 [/LTCG (링크 타임 코드 생성)](/cpp/build/reference/ltcg-link-time-code-generation), 전체 프로그램 최적화 하는 데는 도움이 합니다. 이 스위치는 관리 되는 코드에만 적용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_iSLTCG(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pFlag  
 [out] 반환 `TRUE` 경우는 `compiland` /LTCG 링커 스위치를 사용 하 여 연결 된 그렇지 않으면 반환 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)