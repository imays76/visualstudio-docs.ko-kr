---
title: IEnumDebugPrograms2::Reset | Microsoft Docs
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
- IEnumDebugPrograms2::Reset
helpviewer_keywords:
- IEnumDebugPrograms2::Reset
ms.assetid: b289242b-24ea-4df3-a811-20b0c8a903d6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bae2aba83051dd9832811d2dd6ad6f2858ab47cf
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274146"
---
# <a name="ienumdebugprograms2reset"></a>IEnumDebugPrograms2::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

첫 번째 요소를 열거를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출한 후, 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)

