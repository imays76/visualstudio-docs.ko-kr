---
title: IDebugPortSupplierEx2 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugPortSupplierEx2 interface
ms.assetid: dae0050a-a50a-4f35-bfbd-e538f537b20f
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8deeb9ea6e3f1167a55c77ca8af32e2632d5cbe
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51742626"
---
# <a name="idebugportsupplierex2"></a>IDebugPortSupplierEx2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

포트 공급자를 선택 하 여 핵심 서버와 상호 작용에 대 한 지원을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortSupplierEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 사용자 지정 포트 공급자를 사용 하 여 핵심 서버를 선택할 수 있도록이 인터페이스를 구현 합니다.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다 **IDebugPortSupplierEx2**합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[SetServer](../../../extensibility/debugger/reference/idebugportsupplierex2-setserver.md)|포트 공급자에 대 한 핵심 서버를 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)

