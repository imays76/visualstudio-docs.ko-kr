---
title: IDebugCoreServer3::GetServerFriendlyName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::GetServerFriendlyName
helpviewer_keywords:
- IDebugCoreServer3::GetServerFriendlyName
ms.assetid: 7035b904-b3d7-4d9b-98d9-65714b8a8b9f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 06abe4d0259e06a42aa30465db661f220e40a286
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53892821"
---
# <a name="idebugcoreserver3getserverfriendlyname"></a>IDebugCoreServer3::GetServerFriendlyName
서버에 대 한 친숙 한 이름을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetServerFriendlyName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetServerFriendlyName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrName`  
 [out] 서버에 대 한 친숙 한 이름을 반환합니다.  
  
> [!NOTE]
>  호출자는 문자열을 해제 하는 일을 담당 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 사용자 시작 하는 서버에 대 한이 메서드에서 반환 된 이름은 서버의 전체 이름입니다. 자동 시작 서버 이름은 컴퓨터의 서버가 실행 중인입니다.  
  
 컴퓨터 기반 이름에 대 한 호출을 [GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)