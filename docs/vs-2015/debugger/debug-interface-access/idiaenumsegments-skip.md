---
title: 'Idiaenumsegments:: Skip | Microsoft Docs'
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
- IDiaEnumSegments::Skip method
ms.assetid: ec67039f-da8c-4e70-8db7-957d7d5281e8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e3e92a514c3674fcb012084b127395d23e82b6e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551765"
---
# <a name="idiaenumsegmentsskip"></a>IDiaEnumSegments::Skip
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiaenumsegments:: Skip](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumsegments-skip)합니다.  
  
열거형 시퀀스에서 세그먼트의 지정 된 수를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 건너뛸 열거형 시퀀스에서 세그먼트의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 건너뛸 자세한 세그먼트가 없을 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)



