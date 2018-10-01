---
title: IDebugMemoryContext2::GetInfo | Microsoft Docs
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
- IDebugMemoryContext2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugMemoryContext2::GetInfo method
ms.assetid: 08c7f091-1816-4d64-8834-f9ecaac5c58d
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 94f6d64bdb11fcd930c04a4d50f8cd3b7037bc58
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555872"
---
# <a name="idebugmemorycontext2getinfo"></a>IDebugMemoryContext2::GetInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugMemoryContext2::GetInfo](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorycontext2-getinfo)합니다.  
  
검색을 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) 컨텍스트를 설명 하는 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetInfo(   
   CONTEXT_INFO_FIELDS dwFields,  
   CONTEXT_INFO*       pInfo  
);  
```  
  
```csharp  
int GetInfo(  
   enum_CONTEXT_INFO_FIELDS dwFields,   
   CONTEXT_INFO[]           pinfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFields`  
 [in] 플래그의 조합을 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) 의 필드를 나타내는 열거형을 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) 구조 되 입력 합니다.  
  
 `pInfo`  
 [out에서] `CONTEXT_INFO` 에서 채워진 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)

