---
title: IDebugDefaultPort2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2
helpviewer_keywords:
- IDebugDefaultPort2 interface
ms.assetid: 7b3452af-9a96-4c4c-9946-4339b72d3d7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3f371eb040ae2c160582093f07eacb2108bcb7b7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53930585"
---
# <a name="idebugdefaultport2"></a>IDebugDefaultPort2
이 인터페이스는 포트의 서버 및 알림 기능에 액세스 하기 위한 몇 가지 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDefaultPort2 : IDebugPort2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio 프로그램에 액세스 하기 위한 디버그 포트를 나타내는 데이 인터페이스를 구현 합니다. 또한 사용자 지정 포트 공급자 원격 디버깅을 처리 하는 경우이 인터페이스를 구현할 수 있습니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 인수에 대 한 메서드를 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) 인터페이스는이 인터페이스를 제공 합니다. 호출 [QueryInterface](/cpp/atl/queryinterface) 에 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스는이 인터페이스를 가져올 수도 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 에 정의 된 메서드 외에도 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md),이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)|이 포트에서 포트 알림 인터페이스를 가져옵니다.|  
|[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)|이 포트를 호스팅하는 서버에 인터페이스를 가져옵니다.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugdefaultport2-queryislocal.md)|이 포트는 로컬 컴퓨터에서 실행 중인지 여부를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 이름을 "`IDebugDefaultPort2`" 장기 많은 기본 포트를 나타내지 않습니다. "IDebugPort3." 호출할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)