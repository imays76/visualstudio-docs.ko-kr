---
title: '오류: ASP.NET이 설치 되지 않은 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
ms.assetid: 6286dd3d-3e2b-4edd-959d-81e0ed45500b
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20a6d85fbdc7fad9077a19704b6c448c73dae787
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51739588"
---
# <a name="error-aspnet-not-installed"></a>오류: ASP.NET이 설치되어 있지 않습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 오류는 디버깅하려는 컴퓨터에 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]이 제대로 설치되어 있지 않을 때 발생합니다. [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]이 설치되지 않았거나 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]을 먼저 설치하고 나중에 IIS를 설치했을 수 있습니다.  
  
### <a name="to-reinstall-aspnet"></a>ASP.NET을 다시 설치하려면  
  
1.  명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     여기서 *버전* v1.0.370) 컴퓨터에 설치 된.NET Framework의 버전 번호를 나타냅니다. 프레임 워크 버전을 확인 하 여 확인할 수 있습니다는 `\WINDOWS\Microsoft.NET\Framework` 디렉터리입니다.  
  
    > [!NOTE]
    >  Windows Server 2003을 사용 하 여 설치할 수 있습니다 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 를 사용 하 여 **프로그램 추가 / 제거** 제어판에서.  
  
## <a name="see-also"></a>참고 항목  
 [웹 응용 프로그램 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



