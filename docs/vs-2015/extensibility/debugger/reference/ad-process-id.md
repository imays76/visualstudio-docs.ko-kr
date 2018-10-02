---
title: AD_PROCESS_ID | Microsoft Docs
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
- AD_PROCESS_ID
helpviewer_keywords:
- AD_PROCESS_ID union
ms.assetid: 4cb40d12-2e92-4f09-83f4-689928bd65b3
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 93d50800f77705c24bdc2762be932161779372e7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554009"
---
# <a name="adprocessid"></a>AD_PROCESS_ID
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [AD_PROCESS_ID](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ad-process-id)합니다.  
  
시스템 ID 또는 GUID 일 수 있는 프로세스 ID를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
typedef struct _AD_PROCESS_ID {  
   AD_PROCESS_ID_TYPE ProcessIdType;  
   union {  
      DWORD dwProcessId;   
      GUID  guidProcessId;   
      DWORD dwUnused;   
   } ProcessId;  
} AD_PROCESS_ID;  
```  
  
```csharp  
public struct AD_PROCESS_ID {  
   AD_PROCESS_ID_TYPE ProcessIdType;  
   DWORD              dwProcessId;   
   GUID               guidProcessId;   
   DWORD              dwUnused;   
};  
```  
  
## <a name="members"></a>멤버  
 `ProcessIdType`  
 값을 [AD_PROCESS_ID_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md) 해석 하는 방법을 지정 하는 열거형을 `ProcessId` 공용 구조체 (또는 구조체의 멤버에 액세스를 관리 코드용)입니다.  
  
 dwProcessId  
 시스템에서 값으로 프로세스 ID입니다.  
  
 guidProcessId  
 GUID로 프로세스 ID입니다.  
  
 dwUnused  
 안쪽 여백입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는 다음 메서드에 전달 됩니다.  
  
-   [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)  
  
-   [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)  
  
-   [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)  
  
-   [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)  
  
 다음 방법 중에서 반환 됩니다.  
  
-   [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
-   [GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)   
 [AD_PROCESS_ID_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md)   
 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)   
 [GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)   
 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)   
 [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)

