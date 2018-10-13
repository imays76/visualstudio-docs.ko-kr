---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5380df694196f8a0ec8fea11aefd429ccfeca039
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49239332"
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 사용자는 안전 하지 않은 프로세스에 연결 하려면 먼저 경고를 표시 하려면 포트 공급자를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## <a name="return-value"></a>반환 값  
 반환 값은 아래와 같습니다.  
  
-   `S_OK`: 프로세스에 연결 하는 것이 안전 하 고 경고 대화 상자가 표시 됩니다.  
  
-   `S_FALSE`: 보안 문제일 수 있습니다 연결 하 고 경고 대화 상자가 표시 됩니다.  
  
-   `FAILURE`: 실패 프로세스에 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)

