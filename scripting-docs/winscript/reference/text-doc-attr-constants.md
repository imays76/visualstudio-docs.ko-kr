---
title: TEXT_DOC_ATTR 상수 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- TEXT_DOC_ATTR
apilocation:
- scrobj.dll
helpviewer_keywords:
- TEXT_DOC_ATTR constants
ms.assetid: fd9c53a4-8f73-4c6a-abe5-6b831ecd5b1e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e3fd21ba720dfed394e497a9a56a1bb6898dc60
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348778"
---
# <a name="textdocattr-constants"></a>TEXT_DOC_ATTR 상수
문서의 특성을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef DWORD TEXT_DOC_ATTR;  
```  
  
## <a name="constants"></a>상수  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|TEXT_DOC_ATTR_READONLY|0x00000001|문서는 읽기 전용입니다.|  
|TEXT_DOC_ATTR_TYPE_PRIMARY|0x00000002|이 문서 트리의 주 파일에 문서가 있습니다.|  
|TEXT_DOC_ATTR_TYPE_WORKER|0x00000004|작업자 문서가 있습니다.|  
|TEXT_DOC_ATTR_TYPE_SCRIPT|0x00000008|스크립트 파일에 문서가 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)