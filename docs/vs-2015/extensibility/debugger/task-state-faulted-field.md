---
title: TASK_STATE_FAULTED 필드 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TASK_STATE_FAULTED field, Task class [.NET Framework debug engines]
ms.assetid: ced826ae-09a9-4acf-af00-a2343d396bb8
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 59b5a798efc108324012bcd0b2c38183c3eb09d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564835"
---
# <a name="taskstatefaulted-field"></a>TASK_STATE_FAULTED 필드
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [TASK_STATE_FAULTED 필드](https://docs.microsoft.com/visualstudio/extensibility/debugger/task-state-faulted-field)합니다.  
  
작업이 처리되지 않은 예외 때문에 완료되었습니다.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (mscorlib.dll)  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없는 때문에 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.field static assembly literal int32 TASK_STATE_FAULTED = int32(0x00400000)  
```  
  
## <a name="remarks"></a>설명  
 경우는 [m_stateFlags](../../extensibility/debugger/m-stateflags-field.md) 이 값을 포함 하는 필드를 <xref:System.Threading.Tasks.Task.Status%2A> 속성에서 반환 <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Task 클래스](../../extensibility/debugger/task-class-internal-members.md)

