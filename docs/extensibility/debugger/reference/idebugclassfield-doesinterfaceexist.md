---
title: IDebugClassField::DoesInterfaceExist | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::DoesInterfaceExist
helpviewer_keywords:
- IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8d54afbe331eaf80fedb2dc102f831fcc616fde7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53871358"
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
특정 인터페이스를 클래스에 정의 된 경우를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszInterfaceName`  
 [in] 검색할 인터페이스 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환, S_FALSE를 반환 합니다 인터페이스가 없는 경우 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 적용 모든 인터페이스의 열거형을 가져옵니다 및 일치 하는 인터페이스에 대 한 목록을 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)