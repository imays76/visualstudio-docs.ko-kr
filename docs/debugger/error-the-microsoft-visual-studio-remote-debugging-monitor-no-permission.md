---
title: '오류: 원격 컴퓨터의 Microsoft Visual Studio 원격 디버깅 모니터가 이 컴퓨터에 연결할 수 있는 권한이 없습니다.'
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.error.access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, Windows version error
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4bd5a9ef53940164c7d83dff0159af4c69f61010
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53053434"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>오류: 원격 컴퓨터의 Microsoft Visual Studio 원격 디버깅 모니터가 이 컴퓨터에 연결할 수 있는 권한이 없습니다.
이 오류는 로컬 컴퓨터에 계정이 없는 사용자가 Visual Studio 원격 디버깅 모니터(msvsmon)를 실행하려고 할 때 발생합니다.  
  
### <a name="to-fix-this-problem"></a>이 문제를 해결하려면  
  
- 원격 컴퓨터에서 msvsmon을 실행하는 사용자 계정과 이름 및 암호가 같은 사용자 계정을 Visual Studio 디버거 호스트 컴퓨터에 추가합니다.  
  
   \- 또는 -  
  
- 로컬 컴퓨터에 대한 호출 권한이 있는 사용자로 msvsmon을 실행합니다. 즉, 이 사용자는 msvsmon 컴퓨터의 관리자이자 도메인 사용자여야 합니다. msvsmon을 실행하기 위한 사용자 계정은 다음 두 가지 방법 중 하나로 지정할 수 있습니다.  
  
  - msvsmon 아이콘을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **다음 계정으로 실행**을 선택합니다.  
  
    \- 또는 -  
  
  - 명령 프롬프트에서 `runas.exe`를 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)