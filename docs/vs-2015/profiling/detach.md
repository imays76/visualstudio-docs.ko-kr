---
title: Detach | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9d1b52c-7f28-467d-b1e0-512afc4e46c9
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97e5e64947f2d2807e2d3e34d50827e989ea18e2
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804723"
---
# <a name="detach"></a>Detach
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPerfCmd.exe **Detach** 옵션은 지정된 프로세스 또는 지정되지 않은 경우 모든 프로세서에서 프로파일러의 연결을 끊습니다. 프로파일링은 샘플링 방법을 사용하여 초기화되어야 합니다.  
  
 **Launch** 또는 **Attach** 옵션으로 시작된 프로파일링은 **Detach**로 분리될 수 있습니다. 프로파일러는 후속 **Attach** 명령을 사용하여 다시 연결될 수 있습니다.  
  
 **Detach**는 프로파일링 데이터 파일을 닫지 않습니다. **Shutdown** 옵션을 사용하여 프로파일링을 종료하고 데이터 파일을 닫습니다.  
  
> [!NOTE]
>  **Start** 옵션이 **Crosssession** 옵션으로 지정된 경우 **VSPerfCmd/Attach** 또는 **VSPerfCmd/Detach**에 대한 모든 호출은 **Crosssession**을 지정해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Detach[:PIDs|ProcessNames]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `PIDs|ProcessNames`  
 `PID` - 하나 이상의 프로세스의 숫자 시스템 식별자입니다.  
  
 `ProcessNames` - 프로세스의 이름입니다. 명명된 프로세스의 여러 인스턴스를 실행하는 경우 결과를 예측할 수 없습니다.  
  
 여러 프로세스를 쉼표로 구분합니다.  
  
 프로세스가 지정되지 않은 경우 프로파일러는 프로파일링된 모든 프로세스에서 분리됩니다.  
  
## <a name="valid-options"></a>유효한 옵션  
 다음 **VSPerfCmd** 옵션은 단일 명령줄에서 **Attach** 옵션과 함께 결합될 수 있습니다.  
  
 **Crosssession**  
 로그온 세션 이외의 세션에서 프로파일링 애플리케이션을 활성화합니다. **Start** 옵션이 **Crosssession** 옵션으로 지정된 경우 필요합니다.  
  
## <a name="example"></a>예제  
 이 예제에서 **Detach** 명령은 프로파일링을 일시 중단하고 **Shutdown** 명령은 프로파일러 데이터 파일을 닫습니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
;REM Excercise the application  
VSPerfCmd.exe /Detach  
VSPerfCmd.exe /Shutdown  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 애플리케이션 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 애플리케이션 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)



