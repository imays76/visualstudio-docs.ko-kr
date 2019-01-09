---
title: 'Iactivescriptprofilerheapenum:: Getoptionalinfo 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 99ed9df5-71cf-4c25-b189-af9accc466ee
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bcba1214a0c57e738dec41cdc4976f478802fedc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088805"
---
# <a name="iactivescriptprofilerheapenumgetoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::GetOptionalInfo 메서드
지정된 된 개체의 선택적 정보를 가져옵니다 (힙 개체에서 반환 된 집합에서의 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)).  
  
 반환된 개체에 할당된 반환된 메모리를 해제해서는 안 됩니다. 대신 호출 해야 합니다 [iactivescriptprofilerheapenum:: Freeobjectandoptionalinfo 메서드](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetOptionalInfo (    [in] PROFILER_HEAP_OBJECT* heapObject,    [in] ULONG celt,    [out, size_is(celt)] PROFILER_HEAP_OBJECT_OPTIONAL_INFO* optionalInfo);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `heapObject`  
 합니다 [PROFILER_HEAP_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 의 정보를 반환 합니다.  
  
 `celt`  
 수가 [PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 구조를 반환 합니다.  
  
 `optionalInfo`  
 [out] 배열을 [PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 지정된 된 개체에 대 한 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT입니다.