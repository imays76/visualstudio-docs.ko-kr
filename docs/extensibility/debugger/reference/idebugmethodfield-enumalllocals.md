---
title: IDebugMethodField::EnumAllLocals | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5f03a285a390e244babe99b2cc0ae2db5bf9e67f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53846284"
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
컴파일러에서 내부적으로 생성 된 항목을 포함 하 여 메서드의 모든 로컬 변수에 대 한 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 특정 범위 또는 컨텍스트를 가리키는 메서드 내에서 디버그 주소를 나타내는 개체입니다.  
  
 `ppLocals`  
 [out] 반환 합니다는 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 지정된 된 범위에서 모든 지역 목록을 나타내는 개체;이 고, 그렇지 없는 지역 변수를 나타내는 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 하거나 로컬 항목 없음 없으면 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 지정 된 디버그 주소를 포함 하는 블록 내에 정의 된 변수만 열거 됩니다. 이 메서드는 모든 컴파일러에서 생성 된 지역 변수를 포함합니다. 원본 호출에서에서 명시적으로 정의 된 지역 변수는 필요한 모든 경우는 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) 메서드.  
  
 메서드는 컨텍스트 또는 블록에 대 한 여러 범위를 포함할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)