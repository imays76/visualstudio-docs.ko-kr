---
title: 'Idiaenumsymbols:: Clone | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaEnumSymbols::Clone method
ms.assetid: 5c542025-98cf-4307-901f-b9430f780cf0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f49c20917a1358e461f30ebeaa9fdb9f1d0e4c4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49951550"
---
# <a name="idiaenumsymbolsclone"></a>IDiaEnumSymbols::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumSymbols** ppenum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 ppenum  
 [out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 열거자의 중복을 포함 하는 개체입니다. 기호 중복 되지 열거자만 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)



