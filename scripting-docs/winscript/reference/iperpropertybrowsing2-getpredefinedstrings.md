---
title: IPerPropertyBrowsing2::GetPredefinedStrings | Microsoft 문서
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetPredefinedStrings
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetPredefinedStrings
ms.assetid: d2fa30f7-a566-4dbd-8b47-ffdc00419771
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3bec9643a89d40a7b1e37d019d4211bd7167ee65
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088610"
---
# <a name="iperpropertybrowsing2getpredefinedstrings"></a>IPerPropertyBrowsing2::GetPredefinedStrings
호출자가 목록 상자를 계산된 하는이 속성에 대 한 잠재적인 값을 나타내는 문자열 포인터 배열을 사용 하 여 입력을 허용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetPredefinedStrings(  
   DISPID  dispid,  
   CALPOLESTR*  pCaStrings,  
   CADWORD*  pCaCookies  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dispid`  
 [in] 호출자에 게 요청 하는 문자열 목록 속성의 디스패치 식별자입니다.  
  
 `pCaStrings`  
 [out] 요소 수 및 문자열 포인터 메서드가 할당 한 배열 주소를 포함 하는 호출자에 게 할당 된 계산된 배열 구조에 대 한 포인터입니다. 메서드가 실패 하면 없는 메모리를 할당 및 구조체의 내용을 정의 되지 않습니다.  
  
 `pCaCookies`  
 [out] 요소 수 및 Dword의 메서드가 할당 한 배열 주소를 포함 하는 호출자에 게 할당 된 계산된 배열 구조에 대 한 포인터입니다. 메서드가 실패 하면 없는 메모리를 할당 및 구조체의 내용을 정의 되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## <a name="see-also"></a>참고 항목  
 [IPerPropertyBrowsing2 인터페이스 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)