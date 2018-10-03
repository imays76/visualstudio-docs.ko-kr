---
title: IDebugMemoryContext2::Compare | Microsoft Docs
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
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4219994deb0490533207907d809e970d0fb303cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543631"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugMemoryContext2::Compare](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorycontext2-compare)합니다.  
  
일치 하는 첫 번째 컨텍스트의 인덱스를 반환 하는 비교 플래그를 나타내는 방식으로 지정된 된 배열에 각 컨텍스트에 메모리 컨텍스트를 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Compare(   
   CONTEXT_COMPARE        compare,  
   IDebugMemoryContext2** rgpMemoryContextSet,  
   DWORD                  dwMemoryContextSetLen,  
   DWORD*                 pdwMemoryContext  
);  
```  
  
```csharp  
int Compare(  
   enum_CONTEXT_COMPARE   compare,   
   IDebugMemoryContext2[] rgpMemoryContextSet,   
   uint                   dwMemoryContextSetLen,   
   out uint               pdwMemoryContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `compare`  
 [in] 값을 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) 비교의 형식을 결정 하는 열거형입니다.  
  
 `rgpMemoryContextSet`  
 [in] 배열에 대 한 참조를 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 비교할 개체입니다.  
  
 `dwMemoryContextSetLen`  
 [in] 컨텍스트 수의 `rgpMemoryContextSet` 배열입니다.  
  
 `pdwMemoryContext`  
 [out] 비교를 만족 하는 첫 번째 메모리 컨텍스트의의 인덱스를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 `E_COMPARE_CANNOT_COMPARE` 경우 두 가지 컨텍스트를 비교할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 디버그 엔진 (DE) 모든 유형의 비교를 지원 하지 않아도 되지만 이상을 지원 해야 합니다 `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`하십시오 `CONTEXT_GREATER_THAN` 및 `CONTEXT_SAME_SCOPE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)
