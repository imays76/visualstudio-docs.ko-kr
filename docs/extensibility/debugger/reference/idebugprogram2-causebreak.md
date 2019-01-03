---
title: IDebugProgram2::CauseBreak | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c0e30e90aa1778904bc6c6349427c567ea3bb160
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829672"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
프로그램이 다음 실행을 중지 하는 요청 시간 자신의 스레드 실행 시도 중 하나입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CauseBreak(   
   void   
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) 프로그램은 다음이 메서드가 호출 된 후 코드를 실행 하려고 할 때 이벤트를 보냅니다.  
  
 이 메서드는 비동기 메서드는 반드시 프로그램을 중지 될 때까지 기다리지 않고 즉시 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)