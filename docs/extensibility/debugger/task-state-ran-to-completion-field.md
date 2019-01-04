---
title: TASK_STATE_RAN_TO_COMPLETION 필드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TASK_STATE_RAN_TO_COMPLETION field, Task class [.NET Framework debug engines]
ms.assetid: 0f4830af-fe0c-4141-b768-817f4e426b8c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d4af0b4a2b3ef106aeb57e88440638d2b4a4c904
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53830744"
---
# <a name="taskstaterantocompletion-field"></a>TASK_STATE_RAN_TO_COMPLETION 필드
작업이 실행을 완료했습니다.  
  
 **네임스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (에서 *mscorlib.dll*)  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없는 때문에 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```csharp  
.field static assembly literal int32 TASK_STATE_RAN_TO_COMPLETION = int32(0x02000000)  
```  
  
## <a name="remarks"></a>설명  
 경우는 [m_stateFlags](../../extensibility/debugger/m-stateflags-field.md) 이 값을 포함 하는 필드를 <xref:System.Threading.Tasks.Task.Status%2A> 속성에서 반환 <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Task 클래스](../../extensibility/debugger/task-class-internal-members.md)