---
title: IDebugReference2::GetParent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugReference2::GetParent
helpviewer_keywords:
- IDebugReference2::GetParent
ms.assetid: e3061665-ad3e-4c1b-b33f-82755fa21be3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0c6fe4c6fa66d2a5f8b514028c5633727b003992
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49913036"
---
# <a name="idebugreference2getparent"></a>IDebugReference2::GetParent
참조의 부모 참조를 가져옵니다. 나중에 사용하기 위해 예약되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetParent (   
   IDebugReference2** ppParent  
);  
```  
  
```csharp  
int GetParent (   
   out IDebugReference2 ppParent  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppParent`  
 [out] 반환 된 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 이 속성의 부모를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)