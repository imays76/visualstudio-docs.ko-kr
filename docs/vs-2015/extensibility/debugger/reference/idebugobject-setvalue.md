---
title: IDebugObject::SetValue | Microsoft Docs
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
- IDebugObject::SetValue
helpviewer_keywords:
- IDebugObject::SetValue method
ms.assetid: d652e09c-cdc1-4519-8116-d7c743f5679b
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c47439c69ece059b12ff0d92efd438d73a366915
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553568"
---
# <a name="idebugobjectsetvalue"></a>IDebugObject::SetValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugObject::SetValue](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject-setvalue)합니다.  
  
연속 된 일련의 바이트에서 개체의 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT SetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```csharp  
int SetValue(  
   byte[] pValue,   
   uint   nSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pValue`  
 [in] 새 값을 나타내는 바이트 배열입니다.  
  
 `nSize`  
 [in] 크기 (바이트)에서 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 배열의 값이 복사 됩니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체를 기존 값을 대체 합니다. 새 값의 크기는 기존 값 보다 작거나 클 수 있습니다. 이 `IDebugObject` null 참조일 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)

