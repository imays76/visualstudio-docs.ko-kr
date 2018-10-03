---
title: IDebugBreakpointChecksumRequest2 | Microsoft Docs
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
- IDebugBreakpointChecksumRequest2 interface
ms.assetid: 9cfdbca5-052c-48e9-8411-e2e9e4065d00
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bfccf1afeb521f5557ff20256dfede221ded687a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564360"
---
# <a name="idebugbreakpointchecksumrequest2"></a>IDebugBreakpointChecksumRequest2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugBreakpointChecksumRequest2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbreakpointchecksumrequest2)합니다.  
  
중단점 요청에 대 한 문서 체크섬을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugBreakpointChecksumRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 구현 된 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 패키지를 디버그 하 고 디버그 엔진에서 사용 합니다.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugBreakpointChecksumRequest2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetChecksum](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum.md)|사용할 체크섬 알고리즘의 고유 식별자를 지정 된 중단점 요청에 대 한 문서 체크섬을 검색 합니다.|  
|[IsChecksumEnabled](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-ischecksumenabled.md)|이 문서에 대 한 체크섬을 사용할 수 있는지 확인 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

