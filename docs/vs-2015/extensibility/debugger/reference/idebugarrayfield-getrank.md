---
title: IDebugArrayField::GetRank | Microsoft Docs
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
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c1f06df292c5ed9ed2b7201589f5aa659b3f9716
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49177283"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

순위 또는 배열의 차원 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwRank`  
 [out] 순위를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 배열 차수 차원 수에 해당합니다. C + + 및 C#에서 다차원 배열의 배열은 실제로 배열과 따라서는 1 차원 배열에만 간주 될 수 있습니다 (및 `GetRank` 메서드는 항상 1을 반환). [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], 반면에 다차원 배열 다르게 처리 됩니다 및 차원 수를 반영 하는 이러한 배열 차수 (및 `GetRank` 메서드는 항상 차원 수가 반환).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)

