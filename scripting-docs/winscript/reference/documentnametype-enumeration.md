---
title: DOCUMENTNAMETYPE 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DOCUMENTNAMETYPE
apilocation:
- scrobj.dll
helpviewer_keywords:
- DOCUMENTNAMETYPE enumeration
ms.assetid: d36d550e-efb4-493d-8971-4de267005654
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31e304cfbb0ed7cd19b832d7ed7c33ccc2c930c3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094772"
---
# <a name="documentnametype-enumeration"></a>DOCUMENTNAMETYPE 열거형
문서에 대한 가져올 유형을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef enum tagDOCUMENTNAMETYPE {  
   DOCUMENTNAMETYPE_APPNODE,  
   DOCUMENTNAMETYPE_TITLE,  
   DOCUMENTNAMETYPE_FILE_TAIL,  
   DOCUMENTNAMETYPE_URL,  
DOCUMENTNAMETYPE_UNIQUE_TITLE,} DOCUMENTNAMETYPE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|DOCUMENTNAMETYPE_APPNODE|응용 프로그램 트리에서 표시 된 대로 이름을 가져옵니다.|  
|DOCUMENTNAMETYPE_TITLE|뷰어의 제목 표시줄에 표시 된 대로 이름을 가져옵니다.|  
|DOCUMENTNAMETYPE_FILE_TAIL|경로 없이 파일 이름을 가져옵니다.|  
|DOCUMENTNAMETYPE_URL|문서의 URL을 가져옵니다.|  
|DOCUMENTNAMETYPE_UNIQUE_TITLE|Id에 대 한 열거형을 사용 하 여 추가 된 제목을 가져옵니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)