---
title: IDebugProgramEngines2::EnumPossibleEngines | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
helpviewer_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b3ebf30c4152e03a72626b96cfd51b0341494ccb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891387"
---
# <a name="idebugprogramengines2enumpossibleengines"></a>IDebugProgramEngines2::EnumPossibleEngines
모든 가능한 디버그 엔진 (DE)이이 프로그램을 디버그할 수 있는 Guid를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumPossibleEngines(   
   DWORD  celtBuffer,  
   GUID*  rgguidEngines,  
   DWORD* pceltEngines  
);  
```  
  
```csharp  
int EnumPossibleEngines(   
   uint      celtBuffer,  
   GUID[]    rgguidEngines,  
   ref DWORD pceltEngines  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celtBuffer`  
 [in] 반환할 DE Guid 수입니다. 이 또한의 최대 크기를 지정 된 `rgguidEngines` 배열입니다.  
  
 `rgguidEngines`  
 [out에서] 배열 채울 DE Guid입니다.  
  
 `pceltEngines`  
 [out] 반환 되는 DE Guid의 실제 수를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. [C + +] 반환 `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` 또는 [C#] 0x8007007A 버퍼 크기가 충분 하지 않은 경우.  
  
## <a name="remarks"></a>설명  
 엔진 수를 확인 하기 위해 사용 하 여 한 번이 메서드를 호출 합니다 `celtBuffer` 매개 변수가 0으로 설정 및 `rgguidEngines` 매개 변수가 null 값으로 설정 합니다. 반환 합니다. `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` (C#에 대 한 0x8007007A) 및 `pceltEngines` 매개 변수 버퍼의 필요한 크기를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)