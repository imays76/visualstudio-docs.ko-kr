---
title: CvReleaseProvider 함수 | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkers/CvReleaseProvider
helpviewer_keywords:
- CvReleaseProvider method
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e62e897b56407ab985125361700da60d4e0fdcd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550431"
---
# <a name="cvreleaseprovider-function"></a>CvReleaseProvider 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CvReleaseProvider 함수](https://docs.microsoft.com/visualstudio/profiling/cvreleaseprovider-function)합니다.  
  
표식 공급자를 해제합니다. 표식 공급자 해제가 이 공급자의 이전에 만든 표식 계열에 영향을 주지 않습니다. 표식 계열은 CvReleaseMarkerSeries 호출을 통해 별도로 해제해야 합니다. 공급자를 해제하지 못하면 메모리 누수가 발생합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CvReleaseProvider(  
   _In_ PCV_PROVIDER pProvider  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProvider`  
 공급자 컨텍스트입니다. NULL일 수 없습니다.  
  
## <a name="return-value"></a>반환 값  
 공급자가 성공적으로 해제된 경우 S_OK이고, 오류가 발생한 경우 오류 코드입니다. SUCCEEDED/FAILED 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cvmarkers.h  
  
## <a name="see-also"></a>참고 항목  
 [C++ 라이브러리 참조](../profiling/cpp-library-reference.md)



