---
title: TEXT_DOC_ATTR_2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- TEXT_DOC_ATTR_2
helpviewer_keywords:
- TEXT_DOC_ATTR_2 enumeration
ms.assetid: 2333b33b-042b-4ac6-9ebe-e66f95f52f51
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7d74bbfa4fb89baf01c5fb3d49a0767c67b800ce
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53872728"
---
# <a name="textdocattr2"></a>TEXT_DOC_ATTR_2
문서의 특성을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef DWORD TEXT_DOC_ATTR_2;  
const TEXT_DOC_ATTR_2 TEXT_DOC_ATTR_READONLY_2 = 0x00000001;  
```  
  
```csharp  
public const uint TEXT_DOC_ATTR_READONLY_2 = 0x00000001;  
```  
  
## <a name="members"></a>멤버  
 TEXT_DOC_ATTR_READONLY_2  
 문서 읽기 전용임을 나타냅니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 값의 C# 어셈블리에서 실제로 정의 되지 않았습니다. 대신, 소스 파일에 정의 복사 해야 합니다.  
  
 인수로 전달 된 [onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md)