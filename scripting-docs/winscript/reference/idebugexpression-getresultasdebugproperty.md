---
title: IDebugExpression::GetResultAsDebugProperty | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.GetResultAsDebugProperty
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::GetResultAsDebugProperty
ms.assetid: 9075bf2f-d5bb-464e-b6c2-3fa3215e9ae0
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aebe983c33416d1c3d12d18c272fd1e4de27467
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093108"
---
# <a name="idebugexpressiongetresultasdebugproperty"></a>IDebugExpression::GetResultAsDebugProperty
디버그 속성 및 작업의 반환 값 식 평가의 결과 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetResultAsDebugProperty(  
   HRESULT*          phrResult,  
   IDebugProperty**  ppdp  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phrResult`  
 [out] 작업의 반환 값입니다.  
  
 `ppdp`  
 [out] 식에 대 한 디버그 속성입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_PENDING`|작업이 여전히 보류 중입니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드가 반환으로 식 평가의 결과 `IDebugProperty` 및 작업의 `HRESULT`합니다.  
  
 이 메서드는 반환 `S_OK` 하 고 `phrResult` 반환 `E_ABORT` 경우 `Abort` 작업을 중단 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpression 인터페이스](../../winscript/reference/idebugexpression-interface.md)   
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)