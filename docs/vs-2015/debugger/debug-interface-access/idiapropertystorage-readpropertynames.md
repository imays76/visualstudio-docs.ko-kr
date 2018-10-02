---
title: IDiaPropertyStorage::ReadPropertyNames | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7f20674da015cb31747afc9cce413d3f2290b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541951"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDiaPropertyStorage::ReadPropertyNames](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiapropertystorage-readpropertynames)합니다.  
  
문자열 이름에 해당 하는 검색 속성 식별자를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cpropid`  
 [in] 속성 id 수가 `rgpropid`합니다.  
  
 `rgpropid`  
 [in] 이름을 가져올 속성 id의 배열 (`PROPID` 으로 WTypes.h에 정의 된 한 `ULONG`).  
  
 `rglpwstrName`  
 [out에서] 지정 된 속성 id에 대 한 속성 이름의 배열입니다. 배열 속성 이름의 요청된 수를 보유 하는 미리 할당 해야 하며 이상을 보유할 수 있어야 `cpropid``BSTR` 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 반환 된 속성 이름을 해제 해야 합니다 (호출 하 여는 `SysFreeString` 함수) 더 이상 필요한 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



