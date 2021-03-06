---
title: IProcessDebugManager::RemoveApplication | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProcessDebugManager.RemoveApplication
apilocation:
- pdm.dll
helpviewer_keywords:
- IProcessDebugManager::RemoveApplication
ms.assetid: 334e869d-81ae-4d30-9e89-89763ad4f184
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c163f756e426cab9ce36c1c8343b142bf76aafd6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086517"
---
# <a name="iprocessdebugmanagerremoveapplication"></a>IProcessDebugManager::RemoveApplication
실행 중인 응용 프로그램을 제거 합니다. 응용 프로그램 목록입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT RemoveApplication(  
   DWORD  dwAppCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwAppCookie`  
 [in] 제공 하는 쿠키 `IProcessDebugManager::AddApplication` 응용 프로그램의 응용 프로그램 목록에 추가 될 때입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 실행 중인 응용 프로그램을 제거 응용 프로그램 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Iprocessdebugmanager:: Addapplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)   
 [IProcessDebugManager 인터페이스](../../winscript/reference/iprocessdebugmanager-interface.md)