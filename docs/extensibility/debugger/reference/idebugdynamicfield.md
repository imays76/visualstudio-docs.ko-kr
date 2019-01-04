---
title: IDebugDynamicField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDynamicField
helpviewer_keywords:
- IDebugDynamicField interface
ms.assetid: caffbd95-7596-4714-84b1-b964e89a78bb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8344417bdcb38ec29e183925cedc4da2338ab7a5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53882431"
---
# <a name="idebugdynamicfield"></a>IDebugDynamicField
이 인터페이스에는 변수의 형식을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDynamicField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 런타임 시 결정 될 수 있는 모든 형식에 대 한 기본 클래스로 기호 공급자에 의해 구현 됩니다. 관리 코드 에서만입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 이 인터페이스는 더욱 특수화 된 인터페이스 파생 하는 데 사용 될 수 있는 기본 클래스를 나타냅니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스에서 상속 된 것과 다른 메서드를 제공 하지 않는 `IDebugField`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)