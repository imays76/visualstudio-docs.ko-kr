---
title: SccGetVersion 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b997f3724dc3d1bb0f9155f3b575fef3ce9f2802
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53879629"
---
# <a name="sccgetversion-function"></a>SccGetVersion 함수
이 함수에는 소스 제어 플러그 인에서 지 원하는 원본 제어 플러그 인 API의 버전 번호를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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