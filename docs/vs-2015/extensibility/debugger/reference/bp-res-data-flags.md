---
title: BP_RES_DATA_FLAGS | Microsoft Docs
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
- BP_RES_DATA_FLAGS
helpviewer_keywords:
- BP_RES_DATA_FLAGS enumeration
ms.assetid: d97611e2-def6-45a9-ad7d-eedf2ad4c82b
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f5377478021c9c69a7a7e912163c091849df796c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553508"
---
# <a name="bpresdataflags"></a>BP_RES_DATA_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [BP_RES_DATA_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-res-data-flags)합니다.  
  
데이터 중단점 에뮬레이트 여부 또는에서 구현 된 하드웨어를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_BP_RES_DATA_FLAGS {   
   BP_RES_DATA_EMULATED = 0x0001  
};  
typedef DWORD BP_RES_DATA_FLAGS;  
```  
  
```csharp  
public enum enum_BP_RES_DATA_FLAGS {   
   BP_RES_DATA_EMULATED = 0x0001  
};  
```  
  
## <a name="members"></a>멤버  
 BP_RES_DATA_EMULATED  
 데이터 중단점 에뮬레이트를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 에 사용 되는 합니다 `dwFlags` 의 멤버는 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)

