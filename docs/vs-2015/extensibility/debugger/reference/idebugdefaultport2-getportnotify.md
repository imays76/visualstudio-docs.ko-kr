---
title: IDebugDefaultPort2::GetPortNotify | Microsoft Docs
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
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8684b04b401d9b0a6f068a6425e0e82a4e348f2e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51800551"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드를 가져옵니다는 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 이 포트에 대 한 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```csharp  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppPortNotify`  
 [out] [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 `QueryInterface` 구현 하는 개체에서 메서드를 호출 합니다 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 얻기 위해 인터페이스는 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 인터페이스입니다. 그러나 다른 개체에서 원하는 인터페이스를 구현 하는 경우가 있습니다. 이 메서드는 이러한 상황을 숨깁니다를 반환 합니다 `IDebugPortNotify2` 가장 적합 한 개체의 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)

