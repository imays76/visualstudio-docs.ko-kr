---
title: IDebugArrayField::GetNumberOfElements | Microsoft Docs
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
- IDebugArrayField::GetNumberOfElements
helpviewer_keywords:
- IDebugArrayField::GetNumberOfElements method
ms.assetid: a1961ef3-d69d-4022-b8c9-b9cfb9811345
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a950580417b168796708b0924d756a580bc2b3c6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550707"
---
# <a name="idebugarrayfieldgetnumberofelements"></a>IDebugArrayField::GetNumberOfElements
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugArrayField::GetNumberOfElements](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayfield-getnumberofelements)합니다.  
  
배열의 요소 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetNumberOfElements(   
   DWORD* pdwNumElements  
);  
```  
  
```csharp  
int GetNumberOfElements(  
   out uint pdwNumElements  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwNumElements`  
 [out] 배열의 요소 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 반환 되는 값은 차원 수에 관계 없이 배열에 있는 요소의 총 수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)

