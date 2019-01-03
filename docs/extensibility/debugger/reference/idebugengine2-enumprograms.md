---
title: IDebugEngine2::EnumPrograms | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::EnumPrograms
helpviewer_keywords:
- IDebugEngine2::EnumPrograms
ms.assetid: 56bf98eb-beec-4e5f-9ebe-46c922e54c56
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 89799f5aeb528ca49607f0e321681cf7805b5d60
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53879032"
---
# <a name="idebugengine2enumprograms"></a>IDebugEngine2::EnumPrograms
디버그 엔진 (DE)에서 디버깅 중인 모든 프로그램의 목록을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumPrograms(   
   IEnumDebugPrograms2** ppEnum  
);  
```  
  
```csharp  
int EnumPrograms(   
   out IEnumDebugPrograms2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 반환 된 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md) 는 DE로 디버깅 중인 모든 프로그램의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)