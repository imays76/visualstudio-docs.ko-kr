---
title: 호출 스택 평가 | Microsoft Docs
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
- debugging [Debugging SDK], call stack evaluation
- call stacks, evaluation
ms.assetid: 373d6b49-0459-4cce-816e-05745a44fe49
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e3ab4877a1d6f772572f430c12c436ff5a4b8537
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51772081"
---
# <a name="call-stack-evaluation"></a>호출 스택 평가
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

중단 모드에 있는 동안 호출 스택의 스택 프레임을 보려면 구현 해야 합니다 [EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 메서드.  
  
## <a name="methods-for-evaluation"></a>평가 위한 메서드  
 간단한 디버그 엔진 (DE)에 대 한 스택 프레임을 하나만 있을 수 있습니다. 중단 모드에서 스택 프레임을 검사할의 다음 메서드를 구현 해야 합니다 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|스택 프레임에 대 한 코드 컨텍스트를 가져옵니다. 코드 컨텍스트 스택 프레임의 현재 명령 포인터를 나타냅니다.|  
|[GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|스택 프레임에 대 한 문서 컨텍스트를 가져옵니다. 문서 컨텍스트 스택 프레임에 대 한 소스 코드의 현재 위치를 나타냅니다. 프로그램에서 중지 되 면 소스 코드 보기에 필요 합니다.|  
  
 이러한 메서드는 여러 상황에 맞는 관련 인터페이스 및 메서드 구현의 필요합니다. 따라서 구현 해야 합니다 [GetDocumentContext](../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) 메서드와의 다음 메서드 [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md)합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|문서 컨텍스트 파일 문의 범위를 가져옵니다.|  
  
 코드 컨텍스트 열거의 모든 메서드를 구현 해야 합니다 [IEnumDebugCodeContexts2](../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)

