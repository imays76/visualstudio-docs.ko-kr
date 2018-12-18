---
title: QueryCounters | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f5bedfd794dc7666240b1657cbdc4125b46708b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51809284"
---
# <a name="querycounters"></a>QueryCounters
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**QueryCounters** 옵션은 컴퓨터에서 사용할 수 있는 CPU(하드웨어) 성능 카운터를 나열합니다.  
  
 **QueryCounters**는 명령줄에서 옵션이어야만 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /QueryCounters  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="remarks"></a>설명  
 계측 방법을 사용하는 경우 프로파일러는 각 데이터 컬렉션 이벤트에서 하나 이상의 CPU 성능 카운터의 값을 수집할 수 있습니다. 샘플링 프로파일링 방법을 사용하는 경우 샘플링 간격으로 사용할 하나의 카운터 이벤트와 이벤트 발생 수를 지정할 수 있습니다.  
  
 서로 다른 프로세서는 다른 CPU 성능 카운터를 노출합니다. 프로파일러는 거의 모든 프로세서에서 사용할 수 있는 일반 카운터 집합을 정의합니다. **QueryCounters** 옵션은 일반 카운터의 이름 및 프로세서에 관련된 카운터의 이름을 모두 나열합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)



