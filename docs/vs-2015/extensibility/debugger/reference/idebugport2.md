---
title: IDebugPort2 | Microsoft Docs
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
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f6a3cdbc39ec3575f34e415aa9bbf2e371c66e68
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51800213"
---
# <a name="idebugport2"></a>IDebugPort2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 인터페이스는 시스템에서 디버그 포트를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 사용자 지정 포트 공급자 컴퓨터에서 디버그 포트를 나타내는 데이 인터페이스를 구현 합니다.  
  
 포트에서 송신 포트 이벤트를 지 원하는 경우 해당 구현 해야 합니다는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 지원에 대 한 인터페이스를 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 에서 제공 하는 인터페이스를 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 에 대 한 호출 [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) 하거나 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 요청 된 포트를 나타내는이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPort2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|포트 이름을 반환합니다.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|포트 식별자를 반환합니다.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|(있는 경우) 포트를 만드는 데 요청을 반환 합니다.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|이 포트에 대 한 포트 공급자를 반환합니다.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|프로세스의 식별자를 지정 된 프로세스에는 인터페이스를 반환 합니다.|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|포트에서 실행 중인 모든 프로세스를 열거 합니다.|  
  
## <a name="remarks"></a>설명  
 로컬 포트는 모든 프로세스 및 로컬 컴퓨터에서 실행 중인 프로그램에 대 한 액세스를 제공 합니다. 다른 포트는 Windows CE 기반 장치에 직렬 케이블 연결 또는 DCOM이 아닌 컴퓨터에 네트워크 연결을 나타낼 수 있습니다. `IDebugPort2` 인터페이스는 이름 및 포트의 식별자를 열거 포트에서 실행 중인 모든 프로세스 찾기 및 시작 하 고 포트에서 프로세스 종료에 대 한 기능을 제공 하는 데 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)

