---
title: IActiveScriptProfilerControl5 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7fd0ce34-6ae3-428f-ba90-3e86a8a98ed0
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b20afd05116a98e81a3eeea82e83e6ed200c44a
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349285"
---
# <a name="iactivescriptprofilercontrol5-interface"></a>IActiveScriptProfilerControl5 인터페이스
스크립트 엔진과 연결 된 GC 힙 개체에 대해 열거 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
interface IActiveScriptProfilerControl5 : IActiveScriptProfilerControl4  
```  
  
## <a name="methods"></a>메서드  
 [IActiveScriptProfilerControl5::EnumHeap2 메서드](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md)  
 인터페이스를 반환 합니다 ([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)) 연관된 된 스크립트 엔진의 컨텍스트에서 GC 힙 개체에서 반복을 사용할 수 있는 합니다.