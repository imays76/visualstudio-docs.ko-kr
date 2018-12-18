---
title: 복사 (프로그램 방식 캡처) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ca2d6afc3a5693896c17e49ccb07b5152d906d43
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51776150"
---
# <a name="copy-programmatic-capture"></a>복사(프로그램 방식 캡처)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

활성 그래픽 로그(.vsglog) 파일 내용을 새 파일에 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szNewVSGLog`  
 새 그래픽 로그 파일 이름입니다.  
  
## <a name="remarks"></a>설명  
 그래픽 정보를 새 파일에 복사하려면 이미 캡처한 일부 그래픽 정보가 있어야 합니다. 그렇지 않으면 아무 것도 실행되지 않습니다.



