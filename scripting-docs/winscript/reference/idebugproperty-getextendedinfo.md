---
title: IDebugProperty::GetExtendedInfo | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetExtendedInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetExtendedInfo
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6dc3fc90b8f5fa465715bc4b9466da472cbbb580
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086543"
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
확장 속성에 대 한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cInfos`  
 [in] 확장된 정보 개체의 수입니다.  
  
 `rgguidExtendedInfo`  
 [in] 배열을 `GUID`동시에 여러 확장된 정보 항목을 검색할 수 있도록 s 전달 됩니다.  
  
 `pExtendedInfo`  
 [out] 배열을 반환 `VARIANT`확장된 속성 정보를 검색할 수는 있습니다.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## <a name="remarks"></a>설명  
 이 인터페이스는이 개체에 대 한 정보를 확장을 가져옵니다. API에 적합 하지 않은 자체를 사용 하 여 검색 되는 정보를 검색 하는 목적 으로만 존재 `IDebugProperty::GetPropertyInfo`).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)