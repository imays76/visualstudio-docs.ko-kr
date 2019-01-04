---
title: IDebugSymbolProvider::GetContextFromAddress | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetContextFromAddress
helpviewer_keywords:
- IDebugSymbolProvider::GetContextFromAddress method
ms.assetid: 7a27d56f-20d4-4e5c-af7b-7307d3aff0a1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 161dc0ce94ac2b92d85b29e5c83512ffd25fc49e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53959458"
---
# <a name="idebugsymbolprovidergetcontextfromaddress"></a>IDebugSymbolProvider::GetContextFromAddress
이 메서드는 문서 컨텍스트에 디버그 주소를 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetContextFromAddress(   
   IDebugAddress*           pAddress,  
   IDebugDocumentContext2** ppDocContext  
);  
```  
  
```csharp  
int GetContextFromAddress(  
   IDebugAddress              pAddress,   
   out IDebugDocumentContext2 ppDocContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAddress`  
 [in] 에 표시 된 대로 디버그 주소는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
 `ppDocContext`  
 [out] 에 표시 된 대로 문서 컨텍스트를 반환 합니다는 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)