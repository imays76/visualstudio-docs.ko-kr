---
title: IDiaPropertyStorage::Enum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::Enum
ms.assetid: 00e462da-980a-40b3-a2d6-75a25ee809e5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ff182c2600a41a0e7c13ed460418e93f88baaed
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49871643"
---
# <a name="idiapropertystorageenum"></a>IDiaPropertyStorage::Enum
이 집합 내에서 속성에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Enum (   
   IEnumSTATPROPSTG** ppenum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppenum`  
 [out] 반환 된 `IEnumSTATPROPSTG` 개체 (Microsoft.VisualStudio.OLE.Interop 네임 스페이스) 속성의 열거형을 나타내는입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)