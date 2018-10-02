---
title: 'Idiaenumsymbols:: Item | Microsoft Docs'
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
- IDiaEnumSymbols::Item method
ms.assetid: 2bd1ec04-e677-4e32-8e32-33334f1eed77
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97a5fc4b267fbc62c201f5f23837d37b18bbf0d2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552712"
---
# <a name="idiaenumsymbolsitem"></a>IDiaEnumSymbols::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiaenumsymbols:: Item](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumsymbols-item)합니다.  
  
인덱스를 사용 하 여 기호를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Item (   
   DWORD        index,  
   IDiaSymbol** symbol  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 인덱스입니다.  
 [in] 인덱스를 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 검색 된 개체입니다. 인덱스는 0에서 범위 `count`-1로, 여기서 `count` 반환한를 [idiaenumsymbols:: Get_count](../../debugger/debug-interface-access/idiaenumsymbols-get-count.md) 메서드.  
  
 기호  
 [out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 원하는 기호를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



