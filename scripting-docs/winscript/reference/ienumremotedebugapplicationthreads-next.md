---
title: IEnumRemoteDebugApplicationThreads::Next | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumRemoteDebugApplicationThreads.Next
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumRemoteDebugApplicationThreads::Next
ms.assetid: d8d10d7e-3468-49be-acf9-d842db9940e7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b2aaa1882b5699343d82ecae5fe236574802d7d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092393"
---
# <a name="ienumremotedebugapplicationthreadsnext"></a>IEnumRemoteDebugApplicationThreads::Next
`Next` 메서드 열거형 시퀀스에서 세그먼트의 지정된 된 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Next(  
   ULONG                            celt,  
   IRemoteDebugApplicationThread**  pprdat,  
   ULONG*                           pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 세그먼트 수입니다.  
  
 `pprdat`  
 [out] 배열을 반환 `IRemoteDebugApplicationThread` 검색 되는 세그먼트를 나타내는 인터페이스입니다.  
  
 `pceltFetched`  
 [out] 열거자에서 인출 되는 세그먼트의 실제 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정 된 열거형 시퀀스에서 세그먼트 수를 검색합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumRemoteDebugApplicationThreads 인터페이스](../../winscript/reference/ienumremotedebugapplicationthreads-interface.md)