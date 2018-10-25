---
title: 'Idiaenumsymbols:: Next | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Next method
ms.assetid: bfe5fe27-6a84-4392-910f-e325146d7552
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eaa9f5f1a822660d38f954f4f6bd2ee383cd9a2a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49867483"
---
# <a name="idiaenumsymbolsnext"></a>IDiaEnumSymbols::Next
지정된 된 개수의 열거형 시퀀스에서 기호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Next (   
   ULONG        celt,  
   IDiaSymbol** rgelt,  
   ULONG*       pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 열거자의 기호 수입니다.  
  
 rgelt  
 [out] 배열을 사용 하 여 채울 합니다 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 원하는 기호를 나타내는 개체입니다.  
  
 pceltFetched  
 [out] 페치된 열거자의 기호 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 자세한 기호가 없는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="example"></a>예제  
  
```C++  
IDiaEnumSymbols* pEnum  
CComPtr< IDiaSymbol> pSym;  
DWORD celt;  
pEnum->Next( 1, &pSym, &celt );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession:: Findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)