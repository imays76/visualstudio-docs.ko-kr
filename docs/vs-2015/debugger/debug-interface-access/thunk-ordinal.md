---
title: THUNK_ORDINAL | Microsoft Docs
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
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cf4a6f96eda9a44e10975ffc1a8262030180b302
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542778"
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [THUNK_ORDINAL](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/thunk-ordinal)합니다.  
  
썽크 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
typedef enum THUNK_ORDINAL {   
   THUNK_ORDINAL_NOTYPE,  
   THUNK_ORDINAL_ADJUSTOR,  
   THUNK_ORDINAL_VCALL,  
   THUNK_ORDINAL_PCODE,  
   THUNK_ORDINAL_LOAD   
  
   // trampoline thunk ordinals - only for use in Trampoline thunk symbols  
   THUNK_ORDINAL_TRAMP_INCREMENTAL,  
   THUNK_ORDINAL_TRAMP_BRANCHISLAND,  
} THUNK_ORDINAL;  
```  
  
## <a name="elements"></a>요소  
 THUNK_ORDINAL_NOTYPE  
 표준 썽크 합니다.  
  
 THUNK_ORDINAL_ADJUSTOR  
 `this` 조정기 썽크 합니다.  
  
 THUNK_ORDINAL_VCALL  
 가상 호출 썽크 합니다.  
  
 THUNK_ORDINAL_PCODE  
 P-코드 썽크 합니다.  
  
 THUNK_ORDINAL_LOAD  
 지연 로드 썽크 합니다.  
  
 THUNK_ORDINAL_TRAMP_INCREMENTAL  
 증분 trampoline 썽크 (trampoline 썽크를 다른 메모리 공간에서 호출 반송에 사용 됨).  
  
 THUNK_ORDINAL_TRAMP_BRANCHISLAND  
 분기 지점 trampoline 썽크 합니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값에 대 한 호출에서 반환 되는 [idiasymbol:: Get_thunkordinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)



