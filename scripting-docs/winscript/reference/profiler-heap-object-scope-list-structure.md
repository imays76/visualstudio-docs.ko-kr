---
title: PROFILER_HEAP_OBJECT_SCOPE_LIST 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 33ebaa31-0a35-47d5-a4e3-afd83e16f53e
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 114b1a55fce34908c4274877583164aff4ec8dba
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344826"
---
# <a name="profilerheapobjectscopelist-structure"></a>PROFILER_HEAP_OBJECT_SCOPE_LIST 구조체
이 구조는 함수 개체와 연결 합니다. 범위 목록 함수의 클로저를 범위는 각 범위는 각 지정 된 범위에서 변수를 나타내는 연결 된 속성 목록 가진 힙 개체의 목록을 나타냅니다. 경우에 따라 범위를 사용할 수 없습니다 수의 개체 및 속성 목록에만 해당 인덱스의 이름을 사용할 수 있는 경우  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT_SCOPE_LIST{    UINT count;    [size_is(count)] PROFILER_HEAP_OBJECT_ID scopes[];} PROFILER_HEAP_OBJECT_SCOPE_LIST;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|형식|설명|  
|------------|----------|-----------------|  
|count|UINT|범위 수|  
|scopes|[PROFILER_HEAP_OBJECT_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|배열 범위입니다.|