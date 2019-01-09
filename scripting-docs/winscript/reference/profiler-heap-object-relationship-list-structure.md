---
title: PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 46ca87ea-5b0f-437d-a33f-b2d9a457e036
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3cfbd2f3924391a8c7ff75ea5e4c06e7b0f07c35
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093030"
---
# <a name="profilerheapobjectrelationshiplist-structure"></a>PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST 구조체
힙 개체에 속해 있는 관계의 목록을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST{    UINT count;    [size_is(count)] PROFILER_HEAP_OBJECT_RELATIONSHIP elements[];} PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|형식|설명|  
|------------|----------|-----------------|  
|count|UINT|힙 개체의 관계의 수입니다.|  
|요소|[PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)|힙 개체의 관계입니다.|