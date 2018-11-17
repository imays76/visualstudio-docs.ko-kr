---
title: IEnumDebugErrorBreakpoints2::Clone | Microsoft Docs
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
- IEnumDebugErrorBreakpoints2::Clone
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::Clone
ms.assetid: f6fb4985-8dd6-4a9b-98e0-15dbc64cc9ec
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0c3cdc31ce0a935c0d4140830a1bf59f92615983
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51720626"
---
# <a name="ienumdebugerrorbreakpoints2clone"></a>IEnumDebugErrorBreakpoints2::Clone
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

별도 개체와 현재 열거형의 복사본을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugErrorBreakpoints2** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugErrorBreakpoints2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 이 열거형은 개별 개체로 복사본을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 열거형의 복사본을이 메서드는 시간에 원본과 동일한 상태를 있습니다. 그러나 복사본의 및는 원래 상태는 각각 별도 이며 개별적으로 변경할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)

