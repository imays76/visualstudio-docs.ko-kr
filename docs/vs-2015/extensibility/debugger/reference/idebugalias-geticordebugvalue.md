---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
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
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4e052a720f73ff6df3f716932dba2a1f8ea87c94
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807675"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 별칭을 사용 하 여 연결 된 값을 나타내는 관리 코드 인터페이스를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppUnk`  
 [out] `IUnknown` 이 별칭을 사용 하 여 연결 된 값을 나타내는 인터페이스입니다. 이 인터페이스를 쿼리할 수는 `ICorDebugValue` 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 관리 되는 값에만 적용 됩니다 (합니다 `ICorDebugValue` 은 인터페이스에서 사용할 수 있는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 에 정의 된는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] cordebug.idl 파일에서 SDK).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

