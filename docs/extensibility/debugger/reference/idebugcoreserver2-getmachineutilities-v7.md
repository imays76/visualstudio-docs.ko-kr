---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 265c5b414c53fb6dfe43f63c1016204b8ff02c81
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49908667"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
이 메서드는 서버에 대 한 시스템 유틸리티를 가져옵니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않는: 사용 하지 마세요 ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 항상 반환 `E_NOTIMPL` 이 메서드를 호출 하는 경우). 기록을 위해 보존 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMachineUtilities_V7(  
   IDebugMDMUtil2_V7** ppUtil  
);  
```  
  
```csharp  
int GetMachineUtilities_V7(  
   out IDebugMDMUtil2_V7 ppUtil  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppUtil`  
 [out] 반환 된 `IDebugMDMUtil2_V7` 머신 유틸리티 정보를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 반환 `E_NOTIMPL`, 메서드가 구현 되지 않았음을 나타내는입니다.  
  
## <a name="remarks"></a>설명  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 항상 반환 `E_NOTIMPL` 이 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)