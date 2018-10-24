---
title: DUMPTYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DUMPTYPE
helpviewer_keywords:
- DUMPTYPE enumeration
ms.assetid: ea8160db-8732-4056-a1d7-892ef72da71e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5e886649a7eaa5f9f99eb2e2bfcc48985f12a5e4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949554"
---
# <a name="dumptype"></a>DUMPTYPE
덤프 하는 데 얼마나 많은 프로그램의 상태 (예: 실행 중인 스레드, 스택 프레임 및 현재 명령 주소)를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
typedef DWORD DUMPTYPE;  
```  
  
```csharp  
public enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
```  
  
## <a name="members"></a>멤버  
 DUMP_MINIDUMP  
 작은, compact 덤프를 지정합니다.  
  
 DUMP_FULLDUMP  
 큰, 전체 덤프를 지정합니다.  
  
## <a name="remarks"></a>설명  
 인수로 전달 된 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)