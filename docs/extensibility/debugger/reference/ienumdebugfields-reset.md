---
title: IEnumDebugFields::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugFields::Reset
helpviewer_keywords:
- IEnumDebugFields::Reset method
ms.assetid: 38ff61e4-0120-42e8-971a-16be6050b425
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f1de86cda120d33db201907dca55c07a1c75782
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53839153"
---
# <a name="ienumdebugfieldsreset"></a>IEnumDebugFields::Reset
이 메서드는 첫 번째 요소를 열거형을 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Reset(void);  
```  
  
```csharp  
int Reset();  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출한 다음 호출 후 [다음](../../../extensibility/debugger/reference/ienumdebugfields-next.md) 열거형의 첫 번째 요소를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugfields-next.md)