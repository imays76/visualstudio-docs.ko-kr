---
title: marker_series 클래스 | Microsoft 문서
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e8ecc6a14cce80197c1221734aadb4ce7e6758cf
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53869822"
---
# <a name="markerseries-class"></a>marker_series 클래스
단일 공급자가 생성한 이벤트의 직렬 채널을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
class marker_series;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|name|설명|  
|----------|-----------------|  
|[marker_series::marker_series 생성자](../profiling/marker-series-marker-series-constructor.md)|`marker_series` 클래스의 새 인스턴스를 초기화합니다.|  
|[marker_series::~marker_series 소멸자](../profiling/marker-series-tilde-marker-series-destructor.md)|marker_series 개체를 삭제하고 할당된 모든 리소스를 해제합니다.|  
  
### <a name="public-methods"></a>public 메서드  
  
|name|설명|  
|----------|-----------------|  
|[marker_series::is_enabled 메서드](../profiling/marker-series-is-enabled-method.md)|모든 세션에서 공급자를 사용하도록 설정했는지 확인합니다.|  
|[marker_series::write_alert 메서드](../profiling/marker-series-write-alert-method.md)|동시성 시각화 도우미 추적 파일에 경고를 씁니다.|  
|[marker_series::write_flag 메서드](../profiling/marker-series-write-flag-method.md)|동시성 시각화 도우미 추적 파일에 플래그를 씁니다.|  
|[marker_series::write_message 메서드](../profiling/marker-series-write-message-method.md)|동시성 시각화 도우미 추적 파일에 메시지를 씁니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `marker_series`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** *cvmarkersobj.h*  
  
 **네임스페이스:** Concurrency::diagnostic  
  
## <a name="see-also"></a>참고 항목  
 [진단 네임스페이스](../profiling/diagnostic-namespace.md)