---
title: GETHOSTNAME_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- GETHOSTNAME_TYPE
helpviewer_keywords:
- GETHOSTNAME_TYPE enumeration
ms.assetid: 2be92bea-8133-412b-9015-1833baf16e1b
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 845ec1b24125ee21874efda0b19c956d1e055d8e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49848412"
---
# <a name="gethostnametype"></a>GETHOSTNAME_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

호스트 이름의 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
typedef DWORD GETHOSTNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
```  
  
## <a name="members"></a>멤버  
 GHN_FRIENDLY_NAME  
 호스트의 이름을 지정합니다.  
  
 GHN_FILE_NAME  
 호스트의 파일 이름을 지정합니다.  
  
## <a name="remarks"></a>설명  
 이러한 값을 인수로 전달 되는 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) 다양 한 형식에서 호스트 이름을 검색 하는 방법입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)

