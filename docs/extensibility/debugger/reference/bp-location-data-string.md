---
title: BP_LOCATION_DATA_STRING | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a9f822dfe13d6adf4ea79481ca5bca2cacf2463
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53946942"
---
# <a name="bplocationdatastring"></a>BP_LOCATION_DATA_STRING
통합된 개발 환경 (IDE)에서 사용자가 입력할 수 있는 문자열을 기반으로 하는 데이터 중단점을 설정 하는 것에 대 한 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_LOCATION_DATA_STRING {   
   IDebugThread2* pThread;  
   BSTR           bstrContext;  
   BSTR           bstrDataExpr;  
   DWORD          dwNumElements;  
} BP_LOCATION_DATA_STRING;  
```  
  
## <a name="members"></a>멤버  
 `pThread`  
 합니다 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 중단점이 발생 한 스레드를 나타내는 개체입니다.  
  
 `bstrContext`  
 코드 내에서 중단점, 호출 스택에 표시 된 메서드 또는 함수 이름 일반적으로의 컨텍스트.  
  
 `bstrDataExpr`  
 데이터 문자열 중단점을 설정 하려면 사용자가 입력 합니다.  
  
 `dwNumElements`  
 중단점이 발생 하는 데이터 문자열에 있는 요소의 수입니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 멤버인 합니다 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 공용 구조체의 일부로 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)