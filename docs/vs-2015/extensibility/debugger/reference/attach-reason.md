---
title: ATTACH_REASON | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a59e0c8b0d29529af068b3f0e2aec5f605b7e015
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549704"
---
# <a name="attachreason"></a>ATTACH_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [ATTACH_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/attach-reason)합니다.  
  
프로그램 노드를 연결 하는 디버그 엔진 (DE)에 대 한 이유를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```csharp  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## <a name="members"></a>멤버  
 ATTACH_REASON_AUTO  
 프로세스 디버그 모드에서 현재 이므로 연결 합니다.  
  
 ATTACH_REASON_LAUNCH  
 프로세스가 시작 된 때문에 연결 합니다.  
  
 ATTACH_REASON_USER  
 사용자 요청으로 인해 연결 합니다.  
  
## <a name="remarks"></a>설명  
 이러한 값은 매개 변수로 사용 합니다 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 하 고 [연결](../../../extensibility/debugger/reference/idebugprogramex2-attach.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)

