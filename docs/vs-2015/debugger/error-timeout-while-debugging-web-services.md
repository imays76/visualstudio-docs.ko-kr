---
title: '오류: 웹 서비스를 디버깅 하는 동안 시간 초과 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
- XML Web services, timeout while debugging
ms.assetid: 4b7df112-788a-4429-9a0c-4c6dac4fb609
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 985082d675da2a56d9880414809d91e92cb1fe0d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51736340"
---
# <a name="error-timeout-while-debugging-web-services"></a>오류: 웹 서비스를 디버깅하는 동안 시간이 초과되었습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

코드를 호출하여 XML Web services를 한 단계씩 실행할 때 호출 시간이 초과되어 디버깅을 계속할 수 없는 경우가 있습니다. 이때 다음과 같은 오류 메시지가 나타날 수 있습니다.  
  
```  
An unhandled exception of type 'System.Net.WebException' occurred in   
system.Web.services.dll  
Additional information: The operation has timed-out.  
```  
  
## <a name="solution"></a>솔루션  
 이 문제를 방지하려면 다음 예제와 같이 XML Web services 호출에 대한 시간 제한 값을 무한대로 설정합니다.  
  
```  
Service1 obj = new Service1();  
obj.TimeOut = -1; // infinite time out.  
```  
  
## <a name="see-also"></a>참고 항목  
 [웹 응용 프로그램 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



