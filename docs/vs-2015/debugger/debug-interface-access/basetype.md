---
title: BaseType | Microsoft Docs
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
- BaseType symbol [DIA SDK]
ms.assetid: 2f9e22e6-8360-496a-ac6b-17a5a56b0c46
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5506895f5d03f0be5b31376b5bb0c8d608eeb6e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541350"
---
# <a name="basetype"></a>BaseType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [BaseType](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/basetype)합니다.  
  
기본 형식으로 식별 됩니다 `SymTagBaseType` 기호입니다.  
  
## <a name="properties"></a>속성  
 다음 표에서이 기호 형식에 대 한 추가 올바른 속성을 보여 줍니다.  
  
|속성|데이터 형식|설명|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|`DWORD`|값 중 하나는 [BasicType 열거형](../../debugger/debug-interface-access/basictype.md)합니다.|  
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE` 경우 기본 형식은 const로 표시 됩니다.|  
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`LONGLONG`|크기 (바이트)의 기본 형식입니다.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|기호 묶는 [Compiland](../../debugger/debug-interface-access/compiland.md)합니다.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 기호 ID입니다.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호 인덱스 ID입니다.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagBaseType` (중 하나는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값).|  
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE` 기본 형식에는 정렬 되지 않습니다.|  
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE` 경우 기본 형식 volatile로 표시 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [BasicType 열거형](../../debugger/debug-interface-access/basictype.md)   
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)


