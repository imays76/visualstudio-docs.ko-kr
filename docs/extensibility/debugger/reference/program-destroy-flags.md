---
title: PROGRAM_DESTROY_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- PROGRAM_DESTROY_FLAGS enumeration
ms.assetid: be00d4a3-d5b8-4159-b632-64577f534883
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dcefe5f123717536e951eb3e42f9ae6af1d0865a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53822064"
---
# <a name="programdestroyflags"></a>PROGRAM_DESTROY_FLAGS
유효한 열거 값을 프로그램의 플래그를 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
typedef DWORD PROGRAM_DESTROY_FLAGS;  
```  
  
```csharp  
public enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
```  
  
## <a name="terms"></a>용어  
 PROGRAM_DESTROY_CONTINUE_DEBUGGING  
 프로그램을 삭제 하지만 디버깅을 계속 합니다.  
  
## <a name="remarks"></a>설명  
 열거형에서 반환 되는 [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)