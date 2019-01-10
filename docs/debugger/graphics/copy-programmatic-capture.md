---
title: 복사 (프로그램 방식 캡처) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aab2b18c8c349211f4b5bd26b055d6ee5b65f0c6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990950"
---
# <a name="copy-programmatic-capture"></a>복사(프로그램 방식 캡처)
활성 그래픽 로그(.vsglog) 파일 내용을 새 파일에 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szNewVSGLog`  
 새 그래픽 로그 파일 이름입니다.  
  
## <a name="remarks"></a>주의  
 그래픽 정보를 새 파일에 복사하려면 이미 캡처한 일부 그래픽 정보가 있어야 합니다. 그렇지 않으면 아무 것도 실행되지 않습니다.