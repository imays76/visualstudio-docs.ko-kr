---
title: IDebugBoundBreakpoint2::SetCondition | Microsoft Docs
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
- IDebugBoundBreakpoint2::SetCondition
helpviewer_keywords:
- SetCondition method
- IDebugBoundBreakpoint2::SetCondition method
ms.assetid: 5d366876-efed-43d0-8ea1-dfdb009cbfac
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6b44688268f7c1afcbae097de7371c8142b65053
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51752344"
---
# <a name="idebugboundbreakpoint2setcondition"></a>IDebugBoundBreakpoint2::SetCondition
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

설정 하거나이 바인딩된 중단점과 연결 된 조건을 변경 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
```csharp  
int SetCondition(   
   enum_BP_CONDITION bpCondition  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bpCondition`  
 [in] 값을 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 조건을 설명 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태 설정 됩니다 `BPS_DELETED` (부분 합니다 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형)입니다.  
  
## <a name="remarks"></a>설명  
 이 중단점을 사용 하 여 이전에 연관 된 모든 상태는 손실 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)

