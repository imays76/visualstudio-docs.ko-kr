---
title: IEnumDebugFields | Microsoft Docs
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
- IEnumDebugFields
helpviewer_keywords:
- IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b56a0823ec0c2f02374e46fb8be61277da6adb88
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541375"
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IEnumDebugFields](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugfields)합니다.  
  
이 인터페이스를 구현 하는 개체의 컬렉션을 나타냅니다 합니다 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugFields : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자를 구현 하는 개체의 집합을 제공 하 여이 인터페이스는 구현 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다. 있어 표준 COM 열거형을 아닌지 확인 합니다 [GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md) 메서드.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 이 인터페이스는 반환한 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md) 하 고 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|다음 집합을 검색 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 열거형 개체입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|지정된 된 개수의 항목을 건너뜁니다.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|첫 번째 항목을 열거를 다시 설정합니다.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|현재 열거형의 복사본을 검색 합니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|열거형 항목을 검색합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)   
 [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)

