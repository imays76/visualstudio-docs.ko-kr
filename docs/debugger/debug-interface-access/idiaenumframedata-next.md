---
title: 'Idiaenumframedata:: Next | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6a2c4c2a80ea5186b4a3036491bd64a6531d753
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53951565"
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
열거형 시퀀스에서 프레임 데이터 요소의 지정된 된 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Next (   
   ULONG           celt,   
   IDiaFrameData** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 열거자에 표시 되는 프레임 데이터 요소의 수입니다.  
  
 rgelt  
 [out] 배열을 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 개체를 요청 된 프레임 데이터 요소로 채워집니다.  
  
 pceltFetched  
 [out] 페치된 열거자의 프레임 데이터 요소의 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 레코드가 더 이상 없으면입니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)