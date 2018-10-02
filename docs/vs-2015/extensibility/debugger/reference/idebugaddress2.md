---
title: IDebugAddress2 | Microsoft Docs
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
- IDebugAddress2
helpviewer_keywords:
- IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 988e53c53b83658a2ca4338659a5f805f3bcf0e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555448"
---
# <a name="idebugaddress2"></a>IDebugAddress2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugAddress2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugaddress2)합니다.  
  
이 인터페이스는 주소의 개체를 소유 하는 프로세스의 ID에 대 한 액세스는이 인터페이스에서 표시를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 합니다 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다. 이 인터페이스는이 주소에 관련 된 개체를 소유 하는 프로세스의 id 액세스를 제공 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 사용 하 여 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 에서이 인터페이스를 가져올 수 합니다 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>순서 vtable의 메서드  
 상속 된 메서드 외에 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스에서이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|이 인터페이스를 나타내는 개체를 소유 하는 프로세스의 ID를 검색 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)

