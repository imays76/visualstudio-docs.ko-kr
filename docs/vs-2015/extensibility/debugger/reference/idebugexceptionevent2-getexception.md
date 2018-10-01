---
title: IDebugExceptionEvent2::GetException | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExceptionEvent2::GetException
helpviewer_keywords:
- IDebugExceptionEvent2::GetException
ms.assetid: 7c98f41d-322b-4e72-a514-cbd4823eb70d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b603f7e5b9b42b387df7922068d690762726b0d0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543069"
---
# <a name="idebugexceptionevent2getexception"></a>IDebugExceptionEvent2::GetException
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugExceptionEvent2::GetException](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexceptionevent2-getexception)합니다.  
  
이 이벤트를 발생 시킨 예외에 대 한 자세한 설명을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetException(   
   EXCEPTION_INFO* pExceptionInfo  
);  
```  
  
```csharp  
int GetException(   
   EXCEPTION_INFO[] pExceptionInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pExceptionInfo`  
 [out에서] [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 구조 설명은 예외를 사용 하 여 입력 됩니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 [C + + 전용] 호출자가에서 모든 문자열을 해제 하는 일을 담당 합니다 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) 해제와 구조체를 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 구조의 개체.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

