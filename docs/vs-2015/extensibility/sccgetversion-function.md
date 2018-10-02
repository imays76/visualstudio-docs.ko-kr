---
title: SccGetVersion 함수 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2b5c5e5e6035d6ce0b81ba747efa3cea65ab2f97
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556514"
---
# <a name="sccgetversion-function"></a>SccGetVersion 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [SccGetVersion 함수](https://docs.microsoft.com/visualstudio/extensibility/sccgetversion-function)합니다.  
  
이 함수에는 소스 제어 플러그 인에서 지 원하는 원본 제어 플러그 인 API의 버전 번호를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 `LONG` 지원 되는 원본 제어 플러그 인 API의 버전 번호를 포함 하는 데이터 형식:  
  
|WORD|설명|  
|----------|-----------------|  
|HIWORD|주 버전|  
|LOWORD|부 버전|  
  
## <a name="remarks"></a>설명  
 예를 들어, 소스 제어 플러그 인을 원본 제어 플러그 인 API의 버전 1.3을 지 원하는 경우이 함수는 0x0103를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)

