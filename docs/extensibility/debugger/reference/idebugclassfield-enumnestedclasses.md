---
title: IDebugClassField::EnumNestedClasses | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumNestedClasses
helpviewer_keywords:
- IDebugClassField::EnumNestedClasses method
ms.assetid: 2ba5ef0c-395e-4006-9e3c-9b06e1d711d0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1db2786de20bdb845fb40ed37d4d97f49b718b3c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53908503"
---
# <a name="idebugclassfieldenumnestedclasses"></a>IDebugClassField::EnumNestedClasses
이 클래스에서 중첩 된 클래스에 대 한 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumNestedClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumNestedClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 중첩된 클래스의 목록을 나타내는 개체입니다. 중첩된 클래스에 없는 경우 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 하거나 중첩된 클래스에 없는 경우 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 열거형의 각 요소는 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 중첩된 클래스를 설명 하는 개체입니다.  
  
 중첩된 클래스는 다른 클래스 내에서 정의 되는 클래스입니다. 예를 들어:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 합니다 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 열거형이 나타내는 개체 하나 포함 됩니다는 `NestedClass` 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)