---
title: IDebugObject2::GetBackingFieldForProperty | Microsoft Docs
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
- IDebugObject2::GetBackingFieldForProperty
helpviewer_keywords:
- IDebugObject2::GetBackingFieldForProperty method
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b29b6eb411c511612b60faf271d23decd7370c12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553152"
---
# <a name="idebugobject2getbackingfieldforproperty"></a>IDebugObject2::GetBackingFieldForProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugObject2::GetBackingFieldForProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject2-getbackingfieldforproperty)합니다.  
  
필드 또는 변수 (있는 경우)을 가져옵니다는이 개체가 나타내는 속성을 지 원하는 될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBackingFieldForProperty(  
   IDebugObject2** ppObject  
);  
```  
  
```csharp  
int GetBackingFieldForProperty(  
   out IDebugObject2 ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppObject`  
 [out] [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) 지원 필드를 설명 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 합니다 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) get 사용 하 여 메서드 즉, 관리 코드 클래스 속성을 나타내는 개체 및/또는 set 접근자입니다. 이러한 속성에는 일반적으로 속성에 의해 조작 되는 값을 포함 하는 변수가 필요 합니다. 이 변수는 지원 필드 라고 합니다. 개체에 대 한 지원 필드가 없기 있으면 해야 null 값을 반환 합니다: 일부 호출자가 반환 값에 주의 수 있지만 null 값에서 반환 된 경우 참조 대신 보입니다 `ppObject`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
