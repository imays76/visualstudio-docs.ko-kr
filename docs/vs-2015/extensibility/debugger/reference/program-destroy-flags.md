---
title: PROGRAM_DESTROY_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PROGRAM_DESTROY_FLAGS enumeration
ms.assetid: be00d4a3-d5b8-4159-b632-64577f534883
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c82229526123386f752d723dc432b6e91bba71ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555482"
---
# <a name="programdestroyflags"></a>PROGRAM_DESTROY_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [PROGRAM_DESTROY_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/program-destroy-flags)합니다.  
  
유효한 열거 값을 프로그램의 플래그를 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
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
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)

