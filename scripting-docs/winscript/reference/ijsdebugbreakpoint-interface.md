---
title: IJsDebugBreakPoint 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 791c8488-21e7-46be-b1b4-fe74117cf200
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c43d23d0ba89e6b85a3dd4da688fa89fed4dd99
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093849"
---
# <a name="ijsdebugbreakpoint-interface"></a>IJsDebugBreakPoint 인터페이스
중단점을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
IJsDebugBreakPoint : public IUnknown;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IJsDebugBreakPoint::Delete 메서드](../../winscript/reference/ijsdebugbreakpoint-delete-method.md)|중단점을 삭제합니다.|  
|[IJsDebugBreakPoint::Disable 메서드](../../winscript/reference/ijsdebugbreakpoint-disable-method.md)|중단점을 사용 하지 않도록 설정 합니다.|  
|[IJsDebugBreakPoint::Enable 메서드](../../winscript/reference/ijsdebugbreakpoint-enable-method.md)|중단점을 사용 하도록 설정 합니다.|  
|[IJsDebugBreakPoint::GetDocumentPosition 메서드](../../winscript/reference/ijsdebugbreakpoint-getdocumentposition-method.md)|중단점이 바인딩된 문의 위치를 반환 합니다.|  
|[IJsDebugBreakPoint::IsEnabled 메서드](../../winscript/reference/ijsdebugbreakpoint-isenabled-method.md)|중단점을 설정할지 여부를 결정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)