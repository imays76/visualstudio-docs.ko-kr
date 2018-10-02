---
title: IDebugPortSupplier3::CanPersistPorts | Microsoft Docs
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
- IDebugPortSupplier3::CanPersistPorts
helpviewer_keywords:
- IDebugPortSupplier3::CanPersistPorts
ms.assetid: 4127760c-e602-4e86-9232-457e382a52c7
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4f3799e4003edca0ce2722ad1365777f6be7e43c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553562"
---
# <a name="idebugportsupplier3canpersistports"></a>IDebugPortSupplier3::CanPersistPorts
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugPortSupplier3::CanPersistPorts](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportsupplier3-canpersistports)합니다.  
  
이 메서드는 지속할 지 여부를 포트 공급자 수 포트 (디스크에 쓴 후)에서 디버거는 호출 간에 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanPersistPorts();  
```  
  
```csharp  
int CanPersistPorts();  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 `S_OK` 포트를 유지 하는 경우 또는 `S_FALSE` 나타내는 포트를 유지할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 포트 공급자는 포트를 유지할 수 있습니다, 소멸 될 때 사용자에 게 이렇게 하며 다음 다시 한 번 인스턴스화될 때 다시 로드 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)

