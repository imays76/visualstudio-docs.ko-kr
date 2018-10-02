---
title: IDebugPropertyField::GetPropertySetter | Microsoft Docs
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
- IDebugPropertyField::GetPropertySetter
helpviewer_keywords:
- IDebugPropertyField::GetPropertySetter method
ms.assetid: 744d76fd-2bcc-4917-a040-ce4cc714ef61
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3d3e586b55b72c294eca0cc45fc8af76e4db6e02
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552535"
---
# <a name="idebugpropertyfieldgetpropertysetter"></a>IDebugPropertyField::GetPropertySetter
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugPropertyField::GetPropertySetter](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpropertyfield-getpropertysetter)합니다.  
  
속성을 설정 하는 메서드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetPropertySetter(   
   IDebugMethodField** ppField  
);  
```  
  
```csharp  
int GetPropertySetter(  
   out IDebugMethodField ppField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppField`  
 [out] 반환 된 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) 속성을 설정 하는 메서드를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 Get 속성을 가져오는 메서드를 호출 합니다 [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)

