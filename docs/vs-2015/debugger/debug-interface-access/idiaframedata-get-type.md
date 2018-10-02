---
title: 'Idiaframedata:: Get_type | Microsoft Docs'
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
- IDiaFrameData::get_type method
ms.assetid: efca38b5-c479-4d0a-a164-f903f25c5509
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6585518c3fd1e5120ef1f6f0a2fbb2fec58cce3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552870"
---
# <a name="idiaframedatagettype"></a>IDiaFrameData::get_type
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiaframedata:: Get_type](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-get-type)합니다.  
  
컴파일러 별 프레임 형식을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_type (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 값을 반환 합니다 [StackFrameTypeEnum 열거형](../../debugger/debug-interface-access/stackframetypeenum.md) 컴파일러 별 프레임 형식을 나타내는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [StackFrameTypeEnum 열거형](../../debugger/debug-interface-access/stackframetypeenum.md)



