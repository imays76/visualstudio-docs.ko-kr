---
title: IEnumDebugAddresses::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugAddresses::Skip
helpviewer_keywords:
- IEnumDebugAddresses::Skip method
ms.assetid: ed9a8e71-30ef-414b-9da5-c9a2a251b84e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc9788283b79fd9d1d1460550605fcccf792e7de
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53934864"
---
# <a name="ienumdebugaddressesskip"></a>IEnumDebugAddresses::Skip
이 메서드는 지정 된 개수의 요소를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Skip(  
   [in] ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 건너뛸 요소 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우 `celt` 나머지 요소 수보다 큽니다; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 하는 경우 `celt` 수보다 큰 값 끝에 설정 되어 나머지 요소를 열거 및 `S_FALSE` 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)