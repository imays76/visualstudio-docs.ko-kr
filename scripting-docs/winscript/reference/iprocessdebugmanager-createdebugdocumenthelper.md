---
title: 'Iprocessdebugmanager:: Createdebugdocumenthelper | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProcessDebugManager.CreateDebugDocumentHelper
apilocation:
- pdm.dll
helpviewer_keywords:
- IProcessDebugManager::CreateDebugDocumentHelper
ms.assetid: d644e192-1bcc-4768-a91e-239cd920adcd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62f61f00d2b5f850848efbcf3df65c5a3b10de3c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090485"
---
# <a name="iprocessdebugmanagercreatedebugdocumenthelper"></a>IProcessDebugManager::CreateDebugDocumentHelper
이 응용 프로그램에 대 한 새 디버그 문서 도우미를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CreateDebugDocumentHelper(  
   IUnknown*               punkOuter,  
   IDebugDocumentHelper**  pddh  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `punkOuter`  
 [in] 인 경우 반환 되는 개체를 집계할 수를 `punkOuter` 를 제어 하는 인터페이스 포인터 `IUnknown`합니다. 그렇지 않을 경우 null 포인터입니다.  
  
 `pddh`  
 [out] 이 응용 프로그램에 대 한 디버그 문서 도우미 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는이 응용 프로그램에 대 한 새 디버그 문서 도우미를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [IProcessDebugManager 인터페이스](../../winscript/reference/iprocessdebugmanager-interface.md)