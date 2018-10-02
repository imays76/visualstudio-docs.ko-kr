---
title: IDebugObject2::IsEncOutdated | Microsoft Docs
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
- IDebugObject2::IsEncOutdated
helpviewer_keywords:
- IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 829da5ec42d19a0c938a87dbc51bf10d92d21e55
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553560"
---
# <a name="idebugobject2isencoutdated"></a>IDebugObject2::IsEncOutdated
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugObject2::IsEncOutdated](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject2-isencoutdated)합니다.  
  
이 메서드는 부모 컨테이너 또는이 개체의 편집 하며 계속 하기 상태 최신 인지 확인 합니다. 이 메서드와 항상 반환을 사용자 지정 식 계산기 구현 하지 않는 `E_NOTIMPL`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsEncOutdated(  
   BOOL* pfEncOutdated  
);  
```  
  
```csharp  
int IsEncOutdated(  
   out int pfEncOutdated  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfEncOutdated`  
 [out] 0이 아닌 값 (`TRUE`) 편집 하며 계속 하기 상태를 오래 된 경우에 0 (`FALSE`) 없는 경우.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  사용자 지정 식 계산기는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)

