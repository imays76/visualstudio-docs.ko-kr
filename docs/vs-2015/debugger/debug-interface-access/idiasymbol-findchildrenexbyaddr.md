---
title: IDiaSymbol::findChildrenExByAddr | Microsoft Docs
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
- IDiaSymbol::findChildrenExByAddr
ms.assetid: c1e7885d-2d15-4529-9ac2-32dd22efe31c
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9240828da9f276b1ef440f95e48d1b34432c7f2a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554851"
---
# <a name="idiasymbolfindchildrenexbyaddr"></a>IDiaSymbol::findChildrenExByAddr
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDiaSymbol::findChildrenExByAddr](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-findchildrenexbyaddr)합니다.  
  
지정된 된 주소에서 사용할 수 있는 기호 자식을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT findChildrenExByAddr (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `symtag`  
 [in] 에 정의 된 대로 검색 되는 자식의 기호 태그를 지정 합니다 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)합니다. 로 `SymTagNull` 검색할 모든 자식에 대 한 합니다.  
  
 `name`  
 [in] 검색할 자식 컨트롤의 이름을 지정 합니다. 로 `NULL` 검색할 모든 자식에 대 한 합니다.  
  
 `compareFlags`  
 [in] 이름 일치에 적용할 비교 옵션을 지정 합니다. 값을 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 따로 또는 함께 사용할 수 있습니다.  
  
 `address`  
 [in] 기호의 주소입니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록을 포함 하는 개체 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 기호의 자식이 하나 이상 찾을 하거나 반환 하는 경우 `S_FALSE` 자식이 없는 경우; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 반환 되는 로컬 기호 라이브 범위 정보를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)


