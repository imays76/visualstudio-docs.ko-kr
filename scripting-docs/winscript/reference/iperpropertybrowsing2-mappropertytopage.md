---
title: IPerPropertyBrowsing2::MapPropertyToPage | Microsoft 문서
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.MapPropertyToPage
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::MapPropertyToPage
ms.assetid: e6418a8e-500b-42e1-9b5a-52e6f7567f99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 605c1178ca01c6c55ef170bb4650625bec21c0f8
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087193"
---
# <a name="iperpropertybrowsing2mappropertytopage"></a>IPerPropertyBrowsing2::MapPropertyToPage
이 속성을 편집할 수 있는 속성 페이지의 CLSID를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT MapPropertyToPage(  
   DISPID  dispid,  
   CLSID*  pClsidPropPage  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dispid`  
 [in] 원하는 속성의 식별자를 디스패치하십시오.  
  
 `pClsidPropPage`  
 [out] 속성과 연결 된 속성 페이지를 식별 합니다. CLSID에 대 한 포인터입니다. 이 방법이 실패 하면 *`pClsidPropPage` CLSID_NULL로 설정 됩니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## <a name="see-also"></a>참고 항목  
 [IPerPropertyBrowsing2 인터페이스 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)