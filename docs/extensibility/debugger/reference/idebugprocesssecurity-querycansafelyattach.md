---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a9ecc1d7970fe8be98d199130db6e87847de3aee
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53839007"
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
이 메서드는 사용자는 안전 하지 않은 프로세스에 연결 하려면 먼저 경고를 표시 하려면 포트 공급자를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## <a name="return-value"></a>반환 값  
 반환 값은 아래와 같습니다.  
  
-   `S_OK`: 프로세스에 연결 하는 것이 안전 하 고 경고 대화 상자가 표시 됩니다.  
  
-   `S_FALSE`: 연결 보안 문제가 될 수 하 고 경고 대화 상자가 표시 됩니다.  
  
-   `FAILURE`: 프로세스에 연결 실패 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)