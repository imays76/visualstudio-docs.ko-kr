---
title: IDebugArrayObject::GetRank | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetRank
helpviewer_keywords:
- IDebugArrayObject::GetRank method
ms.assetid: 9948551a-e334-4ff6-979c-08dab633b9b6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7660be0b391208fc52b81796c0a980b079e5aaa2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49875426"
---
# <a name="idebugarrayobjectgetrank"></a>IDebugArrayObject::GetRank
배열의 차원 수, 차수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 사용 된 [GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md) 배열 개체의 각 차원 크기를 검색 하는 방법입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)