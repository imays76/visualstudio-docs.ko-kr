---
title: IDebugPortSupplier2::AddPort | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::AddPort
helpviewer_keywords:
- IDebugPortSupplier2::AddPort
ms.assetid: df491161-6bf3-4fcc-b478-b9ec88ec995f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9db20f2034e1c094beb69a3397261c3522589a6c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867854"
---
# <a name="idebugportsupplier2addport"></a>IDebugPortSupplier2::AddPort
포트를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AddPort(   
   IDebugPortRequest2* pRequest,  
   IDebugPort2**       ppPort  
);  
```  
  
```csharp  
int AddPort(   
   IDebugPortRequest2 pRequest,  
   out IDebugPort2    ppPort  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRequest`  
 [in] [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) 추가할 포트를 설명 하는 개체입니다.  
  
 `ppPort`  
 [out] 반환 된 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 포트를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 실제로 active 포트의 포트 공급자의 내부 목록에 추가할 뿐 아니라 요청 된 포트를 만듭니다. 합니다 [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) 가능한 시간이 많이 걸리는 지연 되지 않도록 하려면 메서드를 처음 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)