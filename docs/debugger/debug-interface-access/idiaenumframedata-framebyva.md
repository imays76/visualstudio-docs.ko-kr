---
title: 'Idiaenumframedata:: Framebyva | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::frameByVA method
ms.assetid: 0b1e441b-710a-46d8-8060-bed39071c834
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f905c3aa380c6decd6687ff2332af2f196d0b68
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851591"
---
# <a name="idiaenumframedataframebyva"></a>IDiaEnumFrameData::frameByVA
가상 주소 (VA) 하 여 프레임을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT frameByVA(   
   ULONGLONG       virtualAddress,  
   IDiaFrameData** frame  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 virtualAddress  
 [in] VA 관심의 프레임입니다.  
  
 프레임  
 [out] 반환 된 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 제공 된 주소가 포함 된 프레임을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 프레임 데이터가 지정 된 주소와 일치 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)