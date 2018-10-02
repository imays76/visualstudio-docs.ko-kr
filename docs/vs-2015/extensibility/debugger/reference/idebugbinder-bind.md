---
title: IDebugBinder::Bind | Microsoft Docs
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
- IDebugBinder::Bind
helpviewer_keywords:
- IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e366ae8044008da51cb2064081abbdc61288ac1b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554300"
---
# <a name="idebugbinderbind"></a>IDebugBinder::Bind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugBinder::Bind](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder-bind)합니다.  
  
이 메서드는 메모리 컨텍스트 또는 기호의 현재 값이 포함 된 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Bind(   
   IDebugObject*  pContainer,  
   IDebugField*   pField,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Bind(  
   IDebugObject     pContainer,  
   IDebugField      pField,  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pContainer`  
 [in] 합니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 자식에서 참조를 포함 하는 `pField`합니다.  
  
 `pField`  
 [in] 합니다 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 기호를 나타내는입니다.  
  
 `ppObject`  
 [out] 반환 된 `IDebugObject` 기호의 인스턴스를 나타내는입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)

