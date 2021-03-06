---
title: ': Kerberos 인증 오류 | Microsoft Docs'
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
- vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c18053f9-9074-4bc3-a8bf-13e4acbea921
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ec03ae3d3b64435877b51996cb84a1768cc4a42
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51732338"
---
# <a name="error-kerberos-authentication-failed"></a>오류: Kerberos 인증에 실패했습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

원격 디버깅을 시작할 때 다음 오류 메시지가 나타날 수 있습니다.  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos auythentication failed.  
```  
  
 이 오류는 로컬 시스템 또는 네트워크 서비스 계정으로 Visual Studio 원격 디버깅 모니터를 실행할 때 발생합니다. 이러한 계정 중 하나를 사용하는 경우 원격 디버거에서는 Kerberos 인증 연결을 설정하여 Visual Studio 디버거 호스트 컴퓨터와 통신해야 합니다.  
  
 다음과 같은 경우에는 Kerberos 인증을 사용할 수 없습니다.  
  
- 대상 컴퓨터 또는 디버거 호스트 컴퓨터가 도메인이 아닌 작업 그룹에 있는 경우  
  
   \- 또는 -  
  
- 도메인 컨트롤러에서 Kerberos가 해제된 경우  
  
  Kerberos 인증을 사용할 수 없는 경우 Visual Studio 원격 디버깅 모니터를 실행하는 데 사용되는 계정을 변경해야 합니다. 프로시저를 참조 하세요 [오류: 대상 컴퓨터의 Visual Studio 원격 디버거 서비스가이 컴퓨터에 다시 연결할 수 없습니다.](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md)합니다.  
  
  두 컴퓨터가 모두 같은 도메인에 연결되어 있는 경우에도 이 메시지가 나타나면 해당 컴퓨터의 DNS에서 디버거 호스트 컴퓨터의 이름을 제대로 확인하고 있는지 검사합니다. 다음 절차를 참조하십시오.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>대상 컴퓨터의 DNS에서 디버거 호스트 컴퓨터 이름을 제대로 확인하고 있는지 검사하려면  
  
1.  대상 컴퓨터에서 엽니다는 **시작** 메뉴에서 **Accessories** 을 클릭 한 다음 **명령 프롬프트**합니다.  
  
2.  에 **명령 프롬프트** 창, 형식:  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3.  `ping` 응답의 첫 번째 줄에는 지정된 컴퓨터의 DNS에서 반환하는 전체 컴퓨터 이름과 IP 주소가 표시됩니다.  
  
4.  디버거 호스트 컴퓨터에서 엽니다는 **명령 프롬프트** 창과 실행 `ipconfig`합니다.  
  
5.  IP 주소 값을 비교합니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)



