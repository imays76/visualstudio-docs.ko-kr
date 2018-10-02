---
title: GetTaskSchedulersForDebugger 메서드 | Microsoft Docs
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
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3d2bc798575cafbeb04837c3065d69b76ee872df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552084"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger 메서드
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [GetTaskSchedulersForDebugger 메서드](https://docs.microsoft.com/visualstudio/extensibility/debugger/gettaskschedulersfordebugger-method)합니다.  
  
모든 배열을 검색 <xref:System.Threading.Tasks.TaskScheduler> 현재 활성화 되어 있는 개체입니다.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (mscorlib.dll)  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없는 때문에 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>반환 값  
 모든 배열의 <xref:System.Threading.Tasks.TaskScheduler> 이 현재 활성 상태인 개체 <xref:System.AppDomain>합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 스레드로부터 안전 하지 않습니다 및 다른 인스턴스의 동시 사용 하지 않아야 <xref:System.Threading.Tasks.TaskScheduler>합니다. 디버거가 다른 모든 스레드가 일시 중단 하는 경우에 디버거를 호출 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TaskScheduler 클래스](../../extensibility/debugger/taskscheduler-class-internal-members.md)

