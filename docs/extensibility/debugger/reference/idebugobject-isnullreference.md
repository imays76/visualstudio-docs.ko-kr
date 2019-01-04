---
title: IDebugObject::IsNullReference | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject::IsNullReference
helpviewer_keywords:
- IDebugObject::IsNullReference method
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 027d6364ad3d6277b716d6716d9d02d1390cde6a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53962943"
---
# <a name="idebugobjectisnullreference"></a>IDebugObject::IsNullReference
이 개체는 null 참조 인지 테스트 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsNullReference(   
   BOOL* pfIsNull  
);  
```  
  
```csharp  
int IsNullReference(  
   out int pfIsNull  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfIsNull`  
 [out] 0이 아닌 값을 반환 합니다 (`TRUE`)이이 개체는 null 참조 이면 그렇지 않으면 0을 반환 합니다 (`FALSE`).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 Null 참조에 할당 되지 않았습니다 하는 개체 또는 빈 개체를 의미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)