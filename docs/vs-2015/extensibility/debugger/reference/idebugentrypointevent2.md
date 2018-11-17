---
title: IDebugEntryPointEvent2 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEntryPointEvent2
helpviewer_keywords:
- IDebugEntryPointEvent2 interface
ms.assetid: a15d1cc3-97b7-438c-8d24-c23149708f42
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7bf5e35251012c12e89e9948f3b0e5f59b337ab3
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51799966"
---
# <a name="idebugentrypointevent2"></a>IDebugEntryPointEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

디버그 엔진 (DE) 프로그램 사용자 코드의 첫 번째 명령은 실행 되려고 할 때 (SDM) 세션 디버그 관리자에 게이 인터페이스를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEntryPointEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE는 정상적인 작업의 일부로이 인터페이스를 구현합니다. 합니다 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 동일한 개체에서 인터페이스를 구현 해야 합니다. SDM 사용 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 액세스는 `IDebugEvent2` 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 DE 만들고 디버깅 중인 프로그램이 로드 되 고 사용자 코드의 첫 번째 명령을 실행할 준비가 되 면이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결할 때 SDM에서 제공 하는 콜백 함수.  
  
## <a name="remarks"></a>설명  
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 프로그램 첫 번째 명령을 실행 하려고 할 때 전송 됩니다. 예를 들어 `IDebugEntryPoint2` 프로그램 사용자의 실행 되려고 할 때 보내집니다 `main` 함수입니다.  
  
 경우는 DE 보냅니다 `IDebugEntryPointEvent2`, 현재 코드 위치 같은 사용자 코드의 첫 번째 명령에서 이어야 합니다 `main`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)

