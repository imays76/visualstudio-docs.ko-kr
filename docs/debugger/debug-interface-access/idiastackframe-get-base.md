---
title: 'Idiastackframe:: Get_base | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_base method
ms.assetid: f27477d7-26fe-4c1c-a08a-c52cb20c8293
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40b3948cdc8d752a6d491b0b094477fdc327f0ea
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956818"
---
# <a name="idiastackframegetbase"></a>IDiaStackFrame::get_base
프레임의 기본 주소를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_base (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 기본 주소를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 속성이 지원 되지 않는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)