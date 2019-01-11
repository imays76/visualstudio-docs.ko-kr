---
title: 'Idiasymbol:: Get_udtkind | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_udtKind method
ms.assetid: 4002f887-aea6-4475-b302-67c57079fe0a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0a95588be4f0a1f37f45a731786ea410a0300f2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967020"
---
# <a name="idiasymbolgetudtkind"></a>IDiaSymbol::get_udtKind
다양 한 사용자 정의 형식 (UDT)을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_udtKind (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 값을 반환 합니다 [UdtKind 열거형](../../debugger/debug-interface-access/udtkind.md) UDT의 종류를 지정 하는 열거형: 구조체, 클래스 또는 공용 구조체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [UdtKind 열거형](../../debugger/debug-interface-access/udtkind.md)