---
title: 검색 식의 논리 연산자 | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Help Viewer 2.0, logical operators in search
- logical operators in search [Help Viewer 2.0]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0cf55bbdc025b4aabd13f7ded72c2ea69386a61b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543160"
---
# <a name="logical-operators-in-search-expressions"></a>검색 식의 논리 연산자
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [검색 식의 논리 연산자](https://docs.microsoft.com/visualstudio/ide/logical-operators-in-search-expressions)합니다.  
  
논리 연산자를 통해 간단한 검색 식에서 복잡한 검색 식을 만들어 콘텐츠 검색을 구체화할 수 있습니다. 다음 표에서 볼 수 있듯이 논리 연산자는 여러 검색어가 검색 쿼리에서 결합되는 방식을 지정합니다.  
  
> [!IMPORTANT]
>  검색 엔진에서 인식할 수 있도록 논리 연산자는 모두 대문자로 입력해야 합니다.  
  
|검색 대상|사용|예제|결과|  
|-------------------|---------|-------------|------------|  
|두 용어가 모두 포함된 항목|AND|dib AND palette|"dib" 및 "palette"를 둘 다 포함하는 항목|  
|두 용어 중 하나가 포함된 항목|또는|raster OR vector|"raster" 또는 "vector"를 포함하는 항목|  
|첫 번째 용어는 있고 두 번째 용어는 없는 항목|NOT|"operating system" NOT DOS|"operating system"을 포함하지만 "DOS"를 포함하지 않는 항목|  
|두 용어가 서로 가까이 있는 항목|근사값|user NEAR kernel|"kernel"의 근접 범위 내에 "user"를 포함하는 항목|  
  
## <a name="see-also"></a>참고 항목  
 [전체 텍스트 검색 팁](../ide/full-text-search-tips.md)   
 [정보 찾기](../ide/locate-information.md)



