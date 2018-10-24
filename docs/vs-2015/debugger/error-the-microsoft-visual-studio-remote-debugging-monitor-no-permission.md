---
title: '오류: Microsoft Visual Studio 원격 디버깅 모니터 원격 컴퓨터에 게이 컴퓨터에 연결할 | Microsoft Docs'
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
- vs.debug.error.access_denied_oncallback
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
- remote debugging, Windows version error
ms.assetid: ba08a59b-6dbc-4bbc-9c52-379d3bf5241f
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20accedd9591c777cad26aed30c05954dfabbdfc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49811091"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>오류: 원격 컴퓨터의 Microsoft Visual Studio 원격 디버깅 모니터가 이 컴퓨터에 연결할 수 있는 권한이 없습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 오류는 로컬 컴퓨터에 계정이 없는 사용자가 Visual Studio 원격 디버깅 모니터(msvsmon)를 실행하려고 할 때 발생합니다.  
  
### <a name="to-fix-this-problem"></a>이 문제를 해결하려면  
  
- 원격 컴퓨터에서 msvsmon을 실행하는 사용자 계정과 이름 및 암호가 같은 사용자 계정을 Visual Studio 디버거 호스트 컴퓨터에 추가합니다.  
  
   \- 또는 -  
  
- 로컬 컴퓨터에 대한 호출 권한이 있는 사용자로 msvsmon을 실행합니다. 즉, 이 사용자는 msvsmon 컴퓨터의 관리자이자 도메인 사용자여야 합니다. msvsmon을 실행하기 위한 사용자 계정은 다음 두 가지 방법 중 하나로 지정할 수 있습니다.  
  
  - Msvsmon 아이콘을 마우스 오른쪽 단추로 클릭 하 고 선택 **실행** 바로 가기 메뉴  
  
    \- 또는 -  
  
  - 명령 프롬프트에서 `runas.exe`를 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [도메인 사이의 원격 디버깅](http://msdn.microsoft.com/library/8e697ce1-55e8-4ab0-a05f-f87225e2f29b)   
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)



