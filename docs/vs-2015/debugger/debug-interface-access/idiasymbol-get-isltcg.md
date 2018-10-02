---
title: 'Idiasymbol:: Get_isltcg | Microsoft Docs'
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
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7651de9c8ed743ecdb9b75a129dd387640890f7d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553838"
---
# <a name="idiasymbolgetisltcg"></a>IDiaSymbol::get_isLTCG
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiasymbol:: Get_isltcg](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-isltcg)합니다.  
  
지정 하는 플래그를 검색 하는지 여부를 [Compiland](../../debugger/debug-interface-access/compiland.md) 링커 스위치를 사용 하 여 연결 되었습니다 [/LTCG (링크 타임 코드 생성)](http://msdn.microsoft.com/library/788c6f52-fdb8-40c2-90af-4026ea2cf2e2), 전체 프로그램 최적화 하는 데는 도움이 합니다. 이 스위치는 관리 되는 코드에만 적용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT get_iSLTCG(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pFlag  
 [out] 반환 `TRUE` 경우는 `compiland` /LTCG 링커 스위치를 사용 하 여 연결 된 그렇지 않으면 반환 `FALSE`합니다.  
  
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



