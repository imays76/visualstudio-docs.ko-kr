---
title: IEnumDebugCustomAttributes::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumCustomAttributes::Reset
helpviewer_keywords:
- IEnumDebugCustomAttributes::Reset
ms.assetid: e0db6518-5a71-4adb-a407-4d2ac7a3e369
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 005791e4e6b21f06d0d3fa761538398ac89db7ce
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53888545"
---
# <a name="ienumdebugcustomattributesreset"></a>IEnumDebugCustomAttributes::Reset
열거형 시퀀스를 시작 부분으로 다시 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Reset(void);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출한 후, 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)