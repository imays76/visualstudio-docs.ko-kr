---
title: IDebugMethodField::GetThis | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMethodField::GetThis
helpviewer_keywords:
- IDebugMethodField::GetThis method
ms.assetid: cc235bea-e909-4d8c-ab54-936736c803fc
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7d942fab313e54497919de03081e7a47aff69ac7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49888805"
---
# <a name="idebugmethodfieldgetthis"></a>IDebugMethodField::GetThis
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

가져옵니다 합니다 `this` (`Me` 에서 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 메서드를 포함 하는 개체의 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetThis(   
   IDebugClassField** ppClass  
);  
```  
  
```csharp  
int GetThis(  
   out IDebugClassField ppClass  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppClass`  
 [out] 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) "this"이 포인터를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 개체 지향 언어의 경우 일반적으로 클래스는 현재 인스턴스화에 대 한 암시적된 포인터 이 이라고 `this` C# / c + +와 `Me` 에서 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)

