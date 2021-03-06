---
title: NotifyDebuggerOfWaitCompletion 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NotifyDebuggerOfWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fabb922101e0995e85173699cd10281ef44e4ba0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51773758"
---
# <a name="notifydebuggerofwaitcompletion-method"></a>NotifyDebuggerOfWaitCompletion 메서드
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

디버거에서 중단점 대상으로 사용 된 자리 표시자 메서드. 이 메서드가 인라인 또는 최적화 된 아니어야 합니다.  
  
 **네임스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (mscorlib.dll)  
  
## <a name="syntax"></a>구문  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## <a name="remarks"></a>설명  
 작업을 사용 하 여 모든 조인 연산이 해당 디버거 알림 비트가 설정 되 면이 메서드를 호출 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
## <a name="see-also"></a>참고 항목  
 [Task 클래스](../../extensibility/debugger/task-class-internal-members.md)

