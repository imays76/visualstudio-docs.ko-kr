---
title: 'Idiasymbol:: Get_inlspec | Microsoft Docs'
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
- IDiaSymbol::get_InlSpec method
ms.assetid: 30af6a2f-be84-429e-a96a-d0f9ed9343fb
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc76fb517c6cc75c6117d8dc7cd95bd377b34f87
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554167"
---
# <a name="idiasymbolgetinlspec"></a>IDiaSymbol::get_InlSpec
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiasymbol:: Get_inlspec](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-inlspec)합니다.  
  
이 함수는 함수를 인라인으로 표시 여부를 나타내는 플래그를 가져옵니다 (중 하나를 사용 합니다 [__inline 인라인 \__forceinline](../../misc/inline-inline-forceinline.md) 특성).  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_inlSpec(  
   BOOL *pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 함수를 인라인으로;로 표시 되어 있으면 반환이 고, 그렇지 `FALSE`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호에 사용할 수 없다는 것을 의미 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [inline, __inline, \__forceinline](../../misc/inline-inline-forceinline.md)



