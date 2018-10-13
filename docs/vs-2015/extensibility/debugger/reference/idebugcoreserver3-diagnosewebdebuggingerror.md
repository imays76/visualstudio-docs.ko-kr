---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs
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
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ec9f0ae560d28304c3d739011e4d6eb509d66d0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49176685"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이유는 auto-attach 확인 하려고 시도 하지 못했습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszUrl`  
 [in] 현재 사용 되지 않은; null 값으로 항상 설정 되어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 다음은 다른 일반적인 반환 코드입니다.  
  
|코드|설명|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|원격 서버 디버깅을 시작 하려면 실패 한 이유를 확인할 수 없습니다.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|권한 부족으로 인해 원격 서버에서 디버깅할 수 없습니다 없거나 DEBUG 동사를 사용할 수 없습니다.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|웹 서버가 잠겨 있기 및 디버깅을 사용 하는 데 필요한 DEBUG 동사를 차단 하는 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)

