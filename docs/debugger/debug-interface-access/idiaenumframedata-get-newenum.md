---
title: 'Idiaenumframedata:: Get__newenum | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::get__NewEnum method
ms.assetid: f5fe0279-0549-4af5-8f89-bcb535fc5809
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f3d436a664d7858fe61dfad64ab539f98e2ed2f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53872085"
---
# <a name="idiaenumframedatagetnewenum"></a>IDiaEnumFrameData::get__NewEnum
검색 된 <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> 이 열거자의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pRetVal  
 [out] 반환 된 `IUnknown` 나타내는 인터페이스입니다는 <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> 이 열거자의 버전.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)