---
title: IDebugProperty2::GetReference | Microsoft Docs
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
- IDebugProperty2::GetReference
helpviewer_keywords:
- IDebugProperty2::GetReference method
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 22d187fb8e5f3c2fd869de5f6472d0e761dd8c8e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541599"
---
# <a name="idebugproperty2getreference"></a>IDebugProperty2::GetReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugProperty2::GetReference](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-getreference)합니다.  
  
속성의 값에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetReference(  
   IDebugReference2** ppReference  
);  
```  
  
```csharp  
int GetReference(  
   out IDebugReference2 ppReference  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppRererence`  
 [out] 반환 된 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 속성의 값에 대 한 참조를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`이 고, 그렇지 않으면 오류 코드를 일반적으로 반환 `E_NOTIMPL` 또는 `E_GETREFERENCE_NO_REFERENCE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)

