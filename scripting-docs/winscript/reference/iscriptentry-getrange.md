---
title: IScriptEntry::GetRange | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetRange
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetRange
ms.assetid: 3ac18f0a-b470-4f4d-b8f5-2da3fdef74f1
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a4e053817ed4c503ebb41e2f3828da421e69ec7
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088740"
---
# <a name="iscriptentrygetrange"></a>IScriptEntry::GetRange
시작 위치와 항목의 길이 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetRange(  
   ULONG              *pichMin  
   ULONG              *pcch  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pichMin`  
 [out] 에 대 한 `IScriptEntry` 스크립트 블록을 지정 하는 개체는 0을 반환 합니다.  
  
 에 대 한 `IScriptEntry` 현재 스크립트 블록의 함수 시작 위치를 반환 하는 함수 개체를 지정 하는 개체입니다.  
  
 에 대 한 `IScriptScriptlet` 개체, 0을 반환 합니다.  
  
 `pcch`  
 [out] 에 대 한 `IScriptEntry` 스크립트 블록을 지정 하는 개체는 텍스트의 길이 반환 합니다.  
  
 에 대 한 `IScriptEntry` 함수 정의의 길이 반환 하는 함수 개체를 지정 하는 개체입니다.  
  
 에 대 한 `IScriptScriptlet` 개체, 항목의 길이 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)