---
title: IDebugProgramDestroyEvent2 | Microsoft Docs
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
- IDebugProgramDestroyEvent2
helpviewer_keywords:
- IDebugProgramDestroyEvent2
ms.assetid: ddf127ca-c4a5-4071-90ca-68faf2f57dbd
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 550c48b7d234cb2cf4afe8d2e4f3b3d9e69f791e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550200"
---
# <a name="idebugprogramdestroyevent2"></a>IDebugProgramDestroyEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugProgramDestroyEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramdestroyevent2)합니다.  
  
이 인터페이스는 프로그램 실행이 완료 하는 경우 디버그 엔진 (DE)에서 세션 디버그 관리자 (SDM)에 전송 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramDestroyEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 또는 사용자 지정 포트 공급자 프로그램 종료 되었습니다 며 디버깅에 사용할 수 있는 더 이상 보고서에이 인터페이스를 구현 합니다. 합니다 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 동일한 개체에서 인터페이스를 구현 해야 합니다. SDM 사용 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 액세스는 `IDebugEvent2` 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 DE 또는 사용자 지정 포트 공급자 만들고이 이벤트 개체는 프로그램의 종료를 보고할를 보냅니다. DE를 사용 하 여이 이벤트를 전송 합니다 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결할 때 SDM에서 제공 하는 콜백 함수. 사용자 지정 포트 공급자 사용 하 여이 이벤트를 전송 합니다 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서 메서드의 `IDebugProgramDestroyEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetExitCode](../../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md)|프로그램의 종료 코드를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)

