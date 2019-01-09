---
title: IEnumDebugCodeContexts::Reset | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugCodeContexts.Reset
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugCodeContexts::Reset
ms.assetid: b7042fac-9f45-46ee-a024-81fed73b0762
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9326ad20c567049242f7f528a7e7c8cf6803882
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091964"
---
# <a name="ienumdebugcodecontextsreset"></a>IEnumDebugCodeContexts::Reset
열거형 시퀀스를 처음으로 다시 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Reset();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수 없이 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드 시작 부분에 열거형 시퀀스를 다시 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugCodeContexts 인터페이스](../../winscript/reference/ienumdebugcodecontexts-interface.md)