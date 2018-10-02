---
title: IEnumDebugFields::GetCount | Microsoft Docs
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
- IEnumDebugFields::GetCount
helpviewer_keywords:
- IEnumDebugFields::GetCount method
ms.assetid: 3f471b40-4db3-49f7-b504-58b2476eef74
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 768aef20f89866d90fd71d2c13c559b19920279a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554628"
---
# <a name="ienumdebugfieldsgetcount"></a>IEnumDebugFields::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IEnumDebugFields::GetCount](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugfields-getcount)합니다.  
  
이 메서드는 열거형의 요소 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetCount(  
   [out] ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcelt`  
 [out] 열거형의 요소 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 다음, 복제, Skip 및 재설정 구현 해야를 지정 하는 일반적인 COM 열거형 인터페이스의 일부가 아닙니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)

