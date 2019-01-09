---
title: ISimpleConnectionPoint::Advise | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.Advise
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::Advise
ms.assetid: 59ded60d-b938-4110-aca3-e69ba234ca9a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b3c0ea37e6fabb051458a11c4838061126bd98bf
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091743"
---
# <a name="isimpleconnectionpointadvise"></a>ISimpleConnectionPoint::Advise
간단한 연결 지점 개체와 클라이언트의 싱크 간에 연결을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Advise(  
   IDispatch*  pdisp,  
   DWORD*      pdwCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdisp`  
 [in] 에 대 한 포인터를 `IDispatch` 클라이언트에서 인터페이스의 싱크는 것이 좋습니다. 클라이언트의 싱크 간단한 연결 지점에서 나가는 호출을 받습니다.  
  
 `pdwCookie`  
 [out] 이 연결을 고유 하 게 식별 하는 반환 된 토큰에 대 한 포인터입니다. 호출자는이 토큰 나중에 전달 하 여 연결을 삭제 하는 `ISimpleConnectionPoint::Unadvise` 메서드. 연결이 성공적으로 설정 되지 않은, 하는 경우이 값은 0입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 간단한 연결 지점 개체와 클라이언트의 싱크 간에 연결을 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)   
 [ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)