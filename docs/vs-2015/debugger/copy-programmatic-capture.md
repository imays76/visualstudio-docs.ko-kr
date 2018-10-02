---
title: 복사 (프로그램 방식 캡처) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 171dd04a4f2c933272a7addc787554f611b1449f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553726"
---
# <a name="copy-programmatic-capture"></a>복사(프로그램 방식 캡처)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [복사 (프로그래밍 방식 캡처)](https://docs.microsoft.com/visualstudio/debugger/graphics/copy-programmatic-capture)합니다.  
  
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



