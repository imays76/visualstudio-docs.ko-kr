---
title: SEEK_START | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SEEK_START
helpviewer_keywords:
- SEEK_START enumeration
ms.assetid: 55bd8901-626e-428b-a263-23b14417f4c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a10d749022757860c6f7cc620091c2ac10623976
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49905224"
---
# <a name="seekstart"></a>SEEK_START
디스어셈블리 스트림에서 검색을 시작 하는 위치를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
typedef DWORD SEEK_START;  
```  
  
```csharp  
public enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
```  
  
## <a name="members"></a>멤버  
 SEEK_START_BEGIN  
 현재 문서의 시작 부분에서 검색을 시작 합니다.  
  
 SEEK_START_END  
 현재 문서의 끝에 검색을 시작 합니다.  
  
 SEEK_START_CURRENT  
 현재 문서의 현재 위치에서 검색을 시작 합니다.  
  
 SEEK_START_CODECONTEXT  
 현재 문서의 컨텍스트에서 지정 된 코드 검색을 시작 합니다.  
  
 SEEK_START_CODELOCID  
 지정 된 코드 위치 식별자에 검색을 시작 합니다. 코드 위치 식별자를 호출 하 여 가져온 [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)합니다.  
  
## <a name="remarks"></a>설명  
 인수로 전달 된 [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [검색](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)   
 [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)