---
title: IDebugExpressionContext2::GetName | Microsoft Docs
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
- IDebugExpressionContext2::GetName
helpviewer_keywords:
- IDebugExpressionContext2::GetName
ms.assetid: c2b70d22-17af-4986-a7e3-930910367216
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a0debd4324b5dcf09a44c9dd9ee803edc9625487
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49858396"
---
# <a name="idebugexpressioncontext2getname"></a>IDebugExpressionContext2::GetName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

평가 컨텍스트에의 이름을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetName(   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName(   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrName`  
 [out] 계산 컨텍스트의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이름에는이 평가 컨텍스트에의 설명입니다. 일반적으로 있는 것이 정확한 평가 컨텍스트를 참조 하는 식 계산기에서 구문 분석할 수 있습니다. 예를 들어, c + +에서 이름이 같습니다.  
  
```  
"{ function-name, source-file-name, module-file-name }"  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)

