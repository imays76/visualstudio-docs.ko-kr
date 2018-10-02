---
title: CvInitProvider 함수 | Microsoft 문서
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
- cvmarkers/CvInitProvider
helpviewer_keywords:
- CvInitProvider method
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a65df9e9ccc61aec0a96f5f467962d46eb88b78c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552854"
---
# <a name="cvinitprovider-function"></a>CvInitProvider 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CvInitProvider 함수](https://docs.microsoft.com/visualstudio/profiling/cvinitprovider-function)합니다.  
  
표식 공급자를 초기화합니다. 여타의 동시성 시각화 도우미 SDK 함수 앞에 호출되어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CvInitProvider(  
   _In_ const GUID* pGuid,  
   _Out_ PCV_PROVIDER* ppProvider  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pGuid`  
 공급자 GUID입니다. NULL일 수 없습니다.  
  
 `ppProvider`  
 공급자 컨텍스트를 저장할 출력 변수의 주소입니다. NULL일 수 없습니다.  
  
## <a name="return-value"></a>반환 값  
 공급자가 성공적으로 초기화된 경우 S_OK이고, 오류가 발생한 경우 오류 코드입니다. SUCCEEDED/FAILED 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cvmarkers.h  
  
## <a name="see-also"></a>참고 항목  
 [C++ 라이브러리 참조](../profiling/cpp-library-reference.md)



