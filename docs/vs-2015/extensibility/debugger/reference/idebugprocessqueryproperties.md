---
title: IDebugProcessQueryProperties | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProcessQueryProperties
ms.assetid: ce29a248-81a0-42c0-99a7-1606e8c548ec
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4ded7950a86409e7f4de0541a182e31b7d000e5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49291489"
---
# <a name="idebugprocessqueryproperties"></a>IDebugProcessQueryProperties
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 인터페이스는 한 확장 인터페이스를 구현한 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 구현 합니다. 구현 자가 디버깅 프로세스 환경에 대 한 정보를 가져올 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProcessQueryProperties: IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버깅 프로세스의 실행 환경에 대 한 정보를 가져오는이 인터페이스를 구현 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProcessQueryProperties`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[QueryProperty](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperty.md)|속성 값을 쿼리 합니다.|  
|[QueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties-queryproperties.md)|속성 값에 대해 쿼리 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 구현 거의 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

