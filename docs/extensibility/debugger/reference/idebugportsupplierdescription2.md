---
title: IDebugPortSupplierDescription2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugPortSupplierDescription2 interface
ms.assetid: dd19b9d6-0703-44b3-9498-cedffa0ce5b7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6387708232c97a25ea11fc554d250e14e6b66e8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53818341"
---
# <a name="idebugportsupplierdescription2"></a>IDebugPortSupplierDescription2
사용 하도록 설정 합니다 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] UI 내에서 텍스트를 표시 하는 **전송 정보** 의 섹션을 **프로세스에 연결** 대화 상자.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortSupplierDescription2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 포트 공급자가 구현 됩니다.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortSupplierDescription2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetDescription](../../../extensibility/debugger/reference/idebugportsupplierdescription2-getdescription.md)|포트 공급자에 대 한 설명 및 설명 메타 데이터를 검색합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll