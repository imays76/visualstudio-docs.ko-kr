---
title: 'Idiainjectedsource:: Get_crc | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_crc method
ms.assetid: 2ecdda93-950e-40d6-b79b-4ae3c55b6cfc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de3864cb92708f0b726ee73316fd2060c981f0a1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53894982"
---
# <a name="idiainjectedsourcegetcrc"></a>IDiaInjectedSource::get_crc
소스 코드의 바이트에서 계산 된 순환 중복 검사 (CRC)를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_crc (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 된 CRC 바이트의 소스 코드에서 계산 됩니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)