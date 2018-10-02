---
title: IDebugReference2::Compare | Microsoft Docs
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
- IDebugReference2::Compare
helpviewer_keywords:
- IDebugReference2::Compare
ms.assetid: 3361c495-2673-4b7c-82e3-dee74e1fa58d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8f61526ac65c947af47bf278029f9f80d72b9a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553161"
---
# <a name="idebugreference2compare"></a>IDebugReference2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugReference2::Compare](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugreference2-compare)합니다.  
  
다른 하나의 참조를 비교합니다. 나중에 사용하기 위해 예약되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Compare (   
   REFERENCE_COMPARE dwCompare,  
   IDebugReference2* pReference  
);  
```  
  
```csharp  
int Compare (   
   enum_REFERENCE_COMPARE dwCompare,  
   IDebugReference2       pReference  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwCompare`  
 [in] 값을 [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md) 는 비교 연산을 수행 하려면 예를 들어, 보다 크거나 같음, 작음,를 지정 하는 열거형입니다.  
  
 `pReference`  
 [in] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 비교에 대 한 참조를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)

