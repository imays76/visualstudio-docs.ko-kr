---
title: IEnumDebugBoundBreakpoints2::Next | Microsoft Docs
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
- IEnumDebugBoundBreakpoints2::Next
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2::Next
ms.assetid: cb3a249f-2282-4bdc-b6d8-a4ee4bfb8365
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1b65975af4dba8a6e79cb86e201cd97819418fe5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542743"
---
# <a name="ienumdebugboundbreakpoints2next"></a>IEnumDebugBoundBreakpoints2::Next
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IEnumDebugBoundBreakpoints2::Next](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugboundbreakpoints2-next)합니다.  
  
열거형에서 다음 요소 집합을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Next(  
   ULONG                    celt,  
   IDebugBoundBreakpoint2** rgelt,  
   ULONG*                   pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint                     celt,  
   IDebugBoundBreakpoint2[] rgelt,  
   ref uint                 pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 요소의 수입니다. 또한 최대 크기를 지정 된 `rgelt` 배열입니다.  
  
 `rgelt`  
 [out에서] 배열을 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 채울 요소입니다.  
  
 `pceltFetched`  
 [out] 에 실제로 반환 된 요소의 수를 반환 합니다. `rgelt`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 요소의 요청 된 수보다 적은; 반환 될 수 있으면이 고, 그렇지 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)   
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)

