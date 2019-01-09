---
title: 콘솔 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9450254620fff8981aa9330dc41535ec69c0d842
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53944141"
---
# <a name="console"></a>콘솔
VSPerfCmd.exe **콘솔** 옵션은 새 명령 프롬프트 창에서 지정된 애플리케이션을 시작합니다. **콘솔**은 VSPerfCmd **Launch** 옵션에만 사용할 수 있습니다. 애플리케이션이 명령줄 애플리케이션이 아닌 경우 **콘솔**에 영향을 주지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /Console  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="required-options"></a>필수 옵션  
 **콘솔**은 **Launch** 옵션도 포함하는 명령줄에서만 지정할 수 있습니다.  
  
 **Launch:** `AppName`  
 프로파일러 및 `AppName`에서 지정한 응용 프로그램을 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 애플리케이션 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 애플리케이션 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)