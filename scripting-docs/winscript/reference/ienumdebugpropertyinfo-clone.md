---
title: IEnumDebugPropertyInfo::Clone | Microsoft 문서
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugPropertyInfo.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugPropertyInfo::Clone
ms.assetid: ba6bdfdb-4c12-475c-bafc-efa6c109d7ee
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b0d172200719a1fe2d95d657fc559f69f7b2ded8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49937229"
---
# <a name="ienumdebugpropertyinfoclone"></a>IEnumDebugPropertyInfo::Clone
현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Clone (  
   IEnumDebugPropertyInfo** ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 복제 된 반환 `IEnumDebugPropertyInfo` 인터페이스.  
  
## <a name="return-value"></a>반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugPropertyInfo 인터페이스](../../winscript/reference/ienumdebugpropertyinfo-interface.md)