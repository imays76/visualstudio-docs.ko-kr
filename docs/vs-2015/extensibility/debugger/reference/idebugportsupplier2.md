---
title: IDebugPortSupplier2 | Microsoft Docs
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
- IDebugPortSupplier2
helpviewer_keywords:
- IDebugPortSupplier2 interface
ms.assetid: 37067324-2ea6-4a01-8829-a6e9c7a70068
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d2e992061fa3486f179e3f498846e0f18b8c1598
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51785133"
---
# <a name="idebugportsupplier2"></a>IDebugPortSupplier2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 인터페이스는 세션 디버그 관리자 (SDM)에 대 한 포트를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortSupplier2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 사용자 지정 포트 공급자 포트 공급자를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 에 대 한 호출 `CoCreateInstance` 포트 공급자를 사용 하 여 `GUID` (이것이이 인터페이스를 검색 하는 일반적인 방법)이이 인터페이스를 반환 합니다. 예를 들어:  
  
```cpp#  
IDebugPortSupplier2 *GetPortSupplier(GUID *pPortSupplierGuid)  
{  
    IDebugPortSupplier2 *pPS = NULL;  
    if (pPortSupplierGuid != NULL) {  
        CComPtr<IDebugPortSupplier2> spPortSupplier;  
        spPortSupplier.CoCreateInstance(*pPortSupplierGuid);  
        if (spPortSupplier != NULL) {  
            pPS = spPortSupplier.Detach();  
        }  
    }  
    return (pPS);  
}  
```  
  
 에 대 한 호출 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md) 이 인터페이스를 사용 하 고 현재 포트 공급자를 나타내는 반환 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]합니다.  
  
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md) 포트를 만든 포트 공급자를 나타내는이 인터페이스를 반환 합니다.  
  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md) 목록을 나타냅니다 `IDebugPortSupplier` 인터페이스 (합니다 `IEnumDebugPortSuppliers` 인터페이스에서 가져온 [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)합니다 를사용하여등록된모든포트공급자를나타내는[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]).  
  
 디버그 엔진을 일반적으로 상호 작용 하지 않습니다 포트 공급자입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortSupplier2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPortSupplierName](../../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)|포트 공급자 이름을 가져옵니다.|  
|[GetPortSupplierId](../../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)|포트 공급자 식별자를 가져옵니다.|  
|[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)|포트 공급자에서 포트를 가져옵니다.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)|이미 존재 하는 포트를 열거 합니다.|  
|[CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)|포트 공급자 새 포트 추가 지원 하는지 확인 합니다.|  
|[AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)|포트를 추가합니다.|  
|[RemovePort](../../../extensibility/debugger/reference/idebugportsupplier2-removeport.md)|포트를 제거합니다.|  
  
## <a name="remarks"></a>설명  
 포트 공급자 수 파악 자체 이름 및 ID, 추가 포트를 제거 하 고 포트 공급자가 제공 하는 모든 포트를 열거 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)   
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)

