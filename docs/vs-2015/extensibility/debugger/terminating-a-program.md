---
title: 프로그램 종료 | Microsoft Docs
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
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e15fa5746b5cd7fae66574ec0d318cad1184cfdd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49861204"
---
# <a name="terminating-a-program"></a>프로그램 종료
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

다음은 하나의 스레드를 사용 하 여 단일 프로그램 종료에 대 한 설명을입니다.  
  
## <a name="termination-process"></a>종료 프로세스  
  
1. DE 보냅니다는 [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) 을 올바른 [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)합니다.  
  
2. DE 보냅니다는 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 을 올바른 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)합니다.  
  
   IDE는 디자인 모드로 전환 됩니다. 디버그 엔진 또는 런타임 환경 호출 [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) 포트에서 프로그램을 제거 하도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)

