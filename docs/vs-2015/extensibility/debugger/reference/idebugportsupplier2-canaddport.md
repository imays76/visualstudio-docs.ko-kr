---
title: IDebugPortSupplier2::CanAddPort | Microsoft Docs
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
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1478841e6fdd48a6c956486153db7bf4e81435fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541636"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugPortSupplier2::CanAddPort](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportsupplier2-canaddport)합니다.  
  
포트 공급자가 새 포트를 추가할 수 있는지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>반환 값  
 포트를 추가할 수 있습니다 하는 경우 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE` 나타내는 포트 없음이 포트 공급자에 추가할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 호출 하기 전에이 메서드를 호출 합니다 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 메서드 하므로 두 번째 방법을 추가 하는 시간이 많이 걸리는 작업 수 뿐만 아니라 포트를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)

