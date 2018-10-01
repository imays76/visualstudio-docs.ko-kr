---
title: 이벤트 소스 (Visual Studio SDK) | Microsoft Docs
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
- debugging [Debugging SDK], event sources
ms.assetid: b9ba0908-ae4c-4a64-aab1-bee453dd7a22
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1fbbe86b12a1833eb61fb2d67a5646cf7c93604c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549573"
---
# <a name="event-sources-visual-studio-sdk"></a>이벤트 소스(Visual Studio SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [이벤트 원본 (Visual Studio SDK)](https://docs.microsoft.com/visualstudio/extensibility/debugger/event-sources-visual-studio-sdk)합니다.  
  
이벤트의 두 원본이: 디버그 엔진 (DE) 및 세션 디버그 관리자 (SDM). SDM에서 전송 되는 이벤트를 NULL 엔진을 설치 하는 동안에 NULL이 아닌 엔진을가 하는 독일에서 전송 되는 이벤트입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 보내는 방법을 보여 줍니다 합니다 **IDebugProgramCreateEvent2** SDM DE에서.  
  
```  
CDebugProgramCreateEvent* pProgramCreateEvent = new CDebugProgramCreateEvent();  
if (FAILED(pCallback->Event(m_pEngine, NULL, m_pProgram, NULL, pProgramCreateEvent, IID_IDebugProgramCreateEvent2, EVENT_ASYNCHRONOUS)))  
{  
   // Handle failure here.  
}  
]  
  
CEvent * pProgCreate = new CEvent(IID_IDebugProgramCreateEvent2, EVENT_ASYNCHRONOUS);    
pProgCreate->SendEvent(pCallback, m_pEngine, (IDebugProgram2 *)this, NULL);  
  
HRESULT CEvent::SendEvent(IDebugEventCallback2 *pCallback, IDebugEngine2 *pEngine, IDebugProgram2 *pProgram, IDebugThread2 *pThread) {    
   HRESULT hr;    
  
   if (m_dwAttrib & EVENT_STOPPING)    
   {    
      hr = SendStoppingEvent(pCallback, pEngine, pProgram, pThread);    
   }    
   else if (m_dwAttrib & EVENT_SYNCHRONOUS)    
   {    
      hr = SendSynchronousEvent(pCallback, pEngine, pProgram, pThread);    
   }    
   else    
   {    
      assert(m_dwAttrib == 0);    
      hr = SendAsynchronousEvent(pCallback, pEngine, pProgram, pThread);    
   }    
  
   return hr;    
}    
  
HRESULT CEvent::SendAsynchronousEvent(IDebugEventCallback2 *pCallback, IDebugEngine2 *pEngine, IDebugProgram2 *pProgram, IDebugThread2 *pThread) {    
  
    HRESULT hr;    
  
   // Make sure the CEvent object running this code is not deleted until the code completes.    
   AddRef();    
  
   pCallback->Event(pEngine, NULL, pProgram, pThread, (IDebugEvent2 *)this, m_riid, m_dwAttrib);    
  
   // No error recovery here.    
   hr = S_OK;     
  
   Release();    
   return hr;    
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 보내기](../../extensibility/debugger/sending-events.md)

