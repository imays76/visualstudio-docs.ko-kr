---
title: IDebugProperty2::GetSize | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetSize
helpviewer_keywords:
- IDebugProperty2::GetSize
ms.assetid: 0deb8ec5-d6fb-4622-bb14-0c46b9459cc6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9371ff0ba43a6d7332649b21363a6b4950097f74
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53855600"
---
# <a name="idebugproperty2getsize"></a>IDebugProperty2::GetSize
속성 값의 바이트에서 크기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSize (   
   DWORD* pdwSize  
);  
```  
  
```csharp  
int GetSize (   
   out uint pdwSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwSize`  
 [out] 속성 값의 바이트에서 크기를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다. 반환 `S_GETSIZE_NO_SIZE` 속성 크기가 없는 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)