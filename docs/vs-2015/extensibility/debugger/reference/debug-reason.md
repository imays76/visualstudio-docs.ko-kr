---
title: DEBUG_REASON | Microsoft Docs
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
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 883630e7c9e00a58eac143a6cde7ee40109bb4e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47565288"
---
# <a name="debugreason"></a>DEBUG_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [DEBUG_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/debug-reason)합니다.  
  
디버깅에 대 한 프로세스를 실행 하는 이유를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
typedef DWORD DEBUG_REASON;  
```  
  
```csharp  
public enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 DEBUG_REASON_ERROR  
 관련 되지 않은 오류가 발생 했습니다 (이 기본 조건으로 맞춤 이유는 다른 경우).  
  
 DEBUG_REASON_USER_LAUNCHED  
 프로세스는 사용자의 요청 시 시작 되었습니다.  
  
 DEBUG_REASON_USER_ATTACHED  
 이미 실행 중인 프로세스에 사용자가 연결 되었습니다.  
  
 DEBUG_REASON_AUTO_ATTACHED  
 프로세스를 시작 될 때 자동으로 연결 됩니다.  
  
 DEBUG_REASON_CAUSALITY  
 로 인해 프로세스가 시작 된를 *Just In Time* (JIT) 디버깅 이벤트입니다.  
  
## <a name="remarks"></a>설명  
 반환 된 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)

