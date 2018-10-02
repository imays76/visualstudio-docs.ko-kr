---
title: 사용자(VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee1a478e-374d-4f30-ae28-d260b9d4723a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b306637cfaa4c58222700f3a1a9b1aaa96b03df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555000"
---
# <a name="user-vsperfcmd"></a>사용자(VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [사용자 (VSPerfCmd)](https://docs.microsoft.com/visualstudio/profiling/user-vsperfcmd)합니다.  
  
**User** 옵션은 프로파일링된 프로세스를 소유한 계정의 도메인 및 사용자 이름을 지정합니다. 이 옵션은 프로세스가 로그온한 사용자 이외의 사용자로 실행 중인 경우에만 필요합니다. [Windows 작업 관리자]의 [프로세스] 탭에 있는 [사용자 이름] 열에 프로세스 소유자가 나열됩니다.  
  
 합니다 **사용자** 옵션 포함 하는 명령줄에서 지정할 수 있습니다 합니다 **시작** 옵션 옵션입니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName /User:[Domain\]UserName [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Domain`  
 사용자 도메인의 이름입니다.  
  
 `UserName`  
 사용자의 이름입니다.  
  
## <a name="required-options"></a>필수 옵션  
 **User** 옵션은 **Start** 옵션에만 사용할 수 있습니다.  
  
 **Start:** `Method`  
 지정된 프로파일링 방법으로 프로파일러를 초기화합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **User** 옵션을 사용하는 방법을 보여 줍니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /User:SYSTEM  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)



