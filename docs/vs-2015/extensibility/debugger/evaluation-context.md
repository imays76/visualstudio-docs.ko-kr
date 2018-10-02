---
title: 평가 컨텍스트에 | Microsoft Docs
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
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 97869b59b657ab4f035e573e87808ca4e86246c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47565256"
---
# <a name="evaluation-context"></a>평가 컨텍스트
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [평가 컨텍스트에](https://docs.microsoft.com/visualstudio/extensibility/debugger/evaluation-context)합니다.  
  
> [!IMPORTANT]
>  Visual Studio 2015에서 식 계산기를 구현 하는 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하세요 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 하 고 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 세 가지 인수를 전달할 디버그 엔진 (DE) 식 계산기 (EE)를 호출 하면 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 다음 표에 나와 있는 것 처럼 찾기 및 평가, 기호에 대 한 컨텍스트를 결정 합니다.  
  
## <a name="arguments"></a>인수  
  
|인수|설명|  
|--------------|-----------------|  
|`pSymbolProvider`|[IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) 기호를 식별 하는 데 사용할 기호 처리기 (SH)를 지정 하는 인터페이스입니다.|  
|`pAddress`|[IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) 현재 실행 지점을 지정 하는 인터페이스입니다. 이 실행 중인 코드를 포함 하는 메서드를 찾을 수 있습니다.|  
|`pBinder`|[IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) 값과 이름이 지정 된 기호의 형식을 찾는 데 사용할 수 있는 인터페이스입니다.|  
  
 `IDebugParsedExpression::EvaluateSync` 반환 합니다는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 결과 값 및 해당 형식을 나타내는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Key 식 계산기 인터페이스](../../extensibility/debugger/key-expression-evaluator-interfaces.md)   
 [로컬 항목 표시](../../extensibility/debugger/displaying-locals.md)   
 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)

