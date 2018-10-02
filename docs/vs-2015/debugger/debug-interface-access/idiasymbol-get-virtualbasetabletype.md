---
title: 'Idiasymbol:: Get_virtualbasetabletype | Microsoft Docs'
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
- IDiaSymbol::get_virtualBaseTableType method
ms.assetid: e0581c4f-0343-49b5-9754-a48477460e9f
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 13dd25c60e373ea747ec802999ce998271ff3e8f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549580"
---
# <a name="idiasymbolgetvirtualbasetabletype"></a>IDiaSymbol::get_virtualBaseTableType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiasymbol:: Get_virtualbasetabletype](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-virtualbasetabletype)합니다.  
  
가상 기본 테이블 포인터의 형식을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_virtualBaseTableType(  
   IDiaSymbol *pRetVal  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`pRetVal`|[out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기본 테이블의 형식을 지정 하는 개체입니다.|  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성 기호를 사용할 수 없는 것을 의미 합니다.  
  
## <a name="remarks"></a>설명  
 가상 기본 테이블 대 한 포인터 (`vbtptr`)에 대 한 숨겨진 포인터가 [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] vtable 가상 기본 클래스에서 상속을 처리 하는 합니다. `vbtptr` 상속 된 클래스에 따라 다양 한 크기를 가질 수 있습니다.  
  
 이 메서드는 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 는 vbtptr의 크기를 결정 하는 데 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



