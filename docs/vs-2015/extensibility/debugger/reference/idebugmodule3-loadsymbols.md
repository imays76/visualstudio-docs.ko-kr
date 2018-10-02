---
title: IDebugModule3::LoadSymbols | Microsoft Docs
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
- IDebugModule3::LoadSymbols
helpviewer_keywords:
- IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f88ff4356b4292cf5b0bec3f066497a7a314b117
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555150"
---
# <a name="idebugmodule3loadsymbols"></a>IDebugModule3::LoadSymbols
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugModule3::LoadSymbols](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmodule3-loadsymbols)합니다.  
  
현재 모듈에 대 한 기호를 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT LoadSymbols(  
   void  
);  
```  
  
```csharp  
int LoadSymbols();  
```  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하는 경우 반환 `S_OK`합니다. 실패 한 경우 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 검색 경로에서 기호 로드 (호출 하 여 변경할 수 있습니다 합니다 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) 메서드).  
  
 이 메서드는 보다 선호 합니다 [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)

