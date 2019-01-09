---
title: IEnumRemoteDebugApplicationThreads::Clone | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumRemoteDebugApplicationThreads.Clone
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumRemoteDebugApplicationThreads::Clone
ms.assetid: d016e7cf-ae73-48ff-aee7-810222e0b05c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e64a83b9cf5184e8a7dfe45cc33b698e5bbdd4f6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091696"
---
# <a name="ienumremotedebugapplicationthreadsclone"></a>IEnumRemoteDebugApplicationThreads::Clone
현재 열거자와 동일한 상태를 포함 하는 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Clone(  
   IEnumRemoteDebugApplicationThreads**  pperdat  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pperdat`  
 [out] 반환 된 `IEnumRemoteDebugApplicationThreads` 열거자의 복제본의 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 열거자와 동일한 상태를 포함 하는 열거자를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumRemoteDebugApplicationThreads 인터페이스](../../winscript/reference/ienumremotedebugapplicationthreads-interface.md)