---
title: IEnumDebugApplicationNodes::Skip | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugApplicationNodes.Skip
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumDebugApplicationNodes::Skip
ms.assetid: b2ad1957-95b5-4c09-9a44-5a765a5308ae
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d13f65a33b40d1c1c3d6ed644865b993469fc6d0
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092133"
---
# <a name="ienumdebugapplicationnodesskip"></a>IEnumDebugApplicationNodes::Skip
열거형 시퀀스에서 세그먼트의 지정 된 수를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 건너뛸 열거형 시퀀스에서 세그먼트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정 된 열거형 시퀀스에서 세그먼트 수를 건너뜁니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugApplicationNodes 인터페이스](../../winscript/reference/ienumdebugapplicationnodes-interface.md)