---
title: IDebugProcessSecurity::GetUserName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fd3f7133652cf048bb1b4c7a2e7d4886b1c79a2b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53931092"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
포트 공급자에서 사용자 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```csharp  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrUserName`  
 [out] 사용자 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하는 경우 반환 `S_OK`합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `GetUserName` 에 표시 되는 사용자 이름을 반환 합니다 **사용자 이름** 열의 합니다 **프로세스에 연결** 대화 상자. 보려는 합니다 **프로세스에 연결** 대화 상자에서 클릭 **프로세스에 연결** 에 **도구** 메뉴에서를 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)