---
title: IDebugProgramNameChangedEvent2 | Microsoft Docs
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
- IDebugProgramNameChangedEvent2 interface
ms.assetid: be1f1cd5-0b2f-435c-a052-dca28a7c978d
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 78c3618edc2ca2e319bcba0e6253ca3408046cfd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49300094"
---
# <a name="idebugprogramnamechangedevent2"></a>IDebugProgramNameChangedEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

프로그램의 이름을 변경 하는 경우 디버그 엔진 (DE)에서 (SDM) 세션 디버그 관리자에 게 전송 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramNameChangedEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 프로그램의 이름이 변경 된 보고서에이 인터페이스를 구현 합니다. 합니다 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 동일한 개체에서 인터페이스를 구현 해야 합니다. SDM 사용 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 액세스 하는 **IDebugEvent2** 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 DE을 만들어 프로그램 이름 변경을 보고 하려면이 이벤트 개체를 보냅니다. DE를 사용 하 여이 이벤트를 전송 합니다 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결할 때 SDM에서 제공 하는 콜백 함수. 사용자 지정 포트 공급자는이 이벤트를 사용 하 여 인터페이스를 보냅니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

