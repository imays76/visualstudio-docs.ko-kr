---
title: IDebugStopCompleteEvent2 | Microsoft Docs
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
- IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b64c9719c6d2975829451dbf11cf584f98805c1b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51780479"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

디버그 엔진 (DE) 프로그램을 중지 하는 경우이 선택적 이벤트 (SDM) 세션 디버그 관리자에 게 보낼 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 새로운 인터페이스는 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]합니다. 이전 릴리스에서 비동기 중지를 지원 하지 않았습니다.  
  
 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) 다중 프로세스 또는 다중 프로그램 시나리오에서 SDM에 의해 호출 됩니다. 한 프로그램 중지 이벤트를 보내면 SDM, SDM을 너무 중지 하려면 다른 프로그램을 요청 합니다.  
  
 비동기적으로 프로그램을 중지 하는 SDM을 알리는 데 사용 됩니다. 이 기능은 유용는 인터프리터 디버그 엔진에 대 한 경우에 따라 코드 없이 실행 되 고 있는 디버그 된 프로그램 내에서 하므로 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) 동기적으로 완료할 수 없습니다. 반환 해야 하는 경우 디버그 엔진을 원하는이 비동기 알림을 사용할 `S_ASYNC_STOP` 에서 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

