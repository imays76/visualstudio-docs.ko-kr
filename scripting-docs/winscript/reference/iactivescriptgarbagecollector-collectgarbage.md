---
title: IActiveScriptGarbageCollector::CollectGarbage | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 478a7a39c69e0c2106e3c6cc308f44f8f7aa3201
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097125"
---
# <a name="iactivescriptgarbagecollectorcollectgarbage"></a>IActiveScriptGarbageCollector::CollectGarbage
액티브 스크립트 호스트는 가비지 수집을 시작 하려면이 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CollectGarbage(        SCRIPTGCTYPE scriptgctype    );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scriptgctype`  
 [in] 합니다 [SCRIPTGCTYPE 열거형](../../winscript/reference/scriptgctype-enumeration.md) 보통 또는 전체 가비지 수집 수행 여부를 지정 하는 합니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptGarbageCollector 인터페이스](../../winscript/reference/iactivescriptgarbagecollector-interface.md)