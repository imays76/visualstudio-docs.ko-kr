---
title: DiaAddressMapEntry | Microsoft Docs
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
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa2824b7fbd10e7628e5c6b0a016615620933df9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51756247"
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

주소 맵에서 항목을 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## <a name="elements"></a>요소  
 `rva`  
 1. 이미지의 상대 가상 주소 (RVA)  
  
 `rvaTo`  
 상대 가상 주소 `rva` 이미지 2.에 매핑된  
  
## <a name="remarks"></a>설명  
 주소 지도 (A)에서 다른 (B) 하나 이미지 레이아웃에서 번역을 제공합니다. 배열을 `DiaAddressMapEntry` 기준으로 정렬 하는 구조 `rva` 주소 지도 정의 합니다.  
  
 주소를 변환할 `addrA`, 주소는 그림과에서 `addrB`, B 이미지에서 다음 단계를 수행:  
  
1. 검색 항목에 대 한 맵을 `e`, 가장 큰 값을 사용 하 여 `rva` 보다 작거나 같음 `addrA`합니다.  
  
2. 설정 `delta = addrA – e.rva`합니다.  
  
3. 설정 `addrB = e.rvaTo + delta`합니다.  
  
   배열을 `DiaAddressMapEntry` 구조에 전달 되는 [idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: dia2.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)



