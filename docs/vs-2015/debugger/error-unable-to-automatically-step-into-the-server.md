---
title: '오류: 단계로 자동으로 서버에 없습니다. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- remote debugging, notification error
ms.assetid: 9a370ccc-d358-429c-b285-9b6c0649bc68
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d75ed4ddb42705b95a5ddd834596bc828e0f3ec2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542084"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>오류: 서버에 대해 자동으로 한 단계씩 코드를 실행할 수 없습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [오류: 자동 단계에는 서버에 없습니다](https://docs.microsoft.com/visualstudio/debugger/error-unable-to-automatically-step-into-the-server)합니다.  
  
이 오류 메시지는 다음과 같습니다.  
  
 서버에 대해 자동으로 한 단계씩 코드를 실행할 수 없습니다. 원격 프로시저가 실행되기 전에 디버거에 알리지 않았습니다.  
  
 이 오류는 웹 서비스를 한 단계씩 실행하려 할 때 발생할 수 있습니다. [한 단계씩 XML Web Services 실행](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)을 참조하세요. 이 오류는 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]이 잘못 설정된 경우에 발생할 수 있습니다.  
  
 가능한 원인은 다음과 같습니다.  
  
-   에 대 한 web.config 파일에 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 응용 프로그램 디버그 "true"로 설정 하지 않습니다 (참조 [ASP.NET 응용 프로그램의 디버그 모드](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
-   버전을 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Visual Studio를 설치한 후 설치 되었습니다. [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Visual Studio 보다 먼저 설치 해야 합니다. 이 문제를 해결하려면 Windows **제어판**, **프로그램 및 기능** 을 사용하여 Visual Studio 설치를 복구합니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [원격 디버깅](../debugger/remote-debugging.md)



