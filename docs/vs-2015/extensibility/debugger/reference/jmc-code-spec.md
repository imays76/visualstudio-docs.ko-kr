---
title: JMC_CODE_SPEC | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- JMC_CODE_SPEC
helpviewer_keywords:
- JMC_CODE_SPEC structure
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ae0c46a59b1f96827bf38b9b036b2044985b797e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49841838"
---
# <a name="jmccodespec"></a>JMC_CODE_SPEC
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 구조는 모듈에 대 한 JustMyCode 정보 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
typedef struct _JMC_CODE_SPEC {  
   BOOL fIsUserCode;  
   BSTR bstrModuleName;  
} JMC_CODE_SPEC;  
```  
  
```csharp  
public struct JMC_CODE_SPEC {  
   public int    fIsUserCode;  
   public string bstrModuleName;  
};  
```  
  
## <a name="members"></a>멤버  
 fIsUserCode  
 0이 아닌 (`TRUE`)이 모듈은 사용자 코드를 고려해 야 하는 경우 0이 고, 그렇지 (`FALSE`) 모듈이 외부 코드로 처리할 수 고를 디버깅할 경우.  
  
 bstrModuleName  
 해당 모듈의 이름입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는 이러한 구조를 목록으로 전달 되는 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)

