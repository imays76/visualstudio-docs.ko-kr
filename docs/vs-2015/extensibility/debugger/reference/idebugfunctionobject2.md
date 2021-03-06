---
title: IDebugFunctionObject2 | Microsoft Docs
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
- IDebugFunctionObject2 interface
ms.assetid: 56b2fdff-146d-4138-a34c-59a9c65a3ddd
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 110b9890e36f8a0100d2cd38b23f445f48cd1cbd
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51770550"
---
# <a name="idebugfunctionobject2"></a>IDebugFunctionObject2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015에서 식 계산기를 구현 하는 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하세요 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 하 고 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 함수를 나타내는 향상 시킬 수는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugFunctionObject2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기 (EE) 함수를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 이 인터페이스의 메서드 연기 **IDebugFunctionObject** 다음과 같은 방법으로:  
  
-   합니다 **IDebugEvaluate** 메서드는 플래그를 사용 합니다.  
  
-   합니다 **CreateObject** 메서드는 제한 시간 및 플래그를 사용 합니다.  
  
-   합니다 **CreateStringObjectWithLength** 메서드는 길이 사용 합니다.  
  
## <a name="methods"></a>메서드  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject2-createobject.md)|평가 플래그 설정 및 제한 시간 값을 지정 하는 생성자를 사용 하는 개체를 만듭니다.|  
|[CreateStringObjectWithLength](../../../extensibility/debugger/reference/idebugfunctionobject2-createstringobjectwithlength.md)|지정 된 길이가 지정 된 문자열 개체를 만듭니다.|  
|[Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject2-evaluate.md)|함수를 호출 하 고 결과 개체 값을 반환 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

