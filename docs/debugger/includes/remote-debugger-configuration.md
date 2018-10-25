---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 252c505260986bd08b5522ba79d1e00a82624241
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942961"
---
원격 컴퓨터에서 관리 권한이 있어야 합니다.  
  
1. 원격 디버거 응용 프로그램을 찾습니다. (이 설치 되어 있는, 위치에서 msvsmon.exe를 찾거나 시작 메뉴 및 검색을 엽니다 **원격 디버거**.)
  
    원격 서버에서 원격 디버거를 실행 하는 경우 원격 디버거 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 있습니다 **관리자 권한으로 실행**합니다. 원격 서버에서 실행 하지 않는 경우만 해당 정상적으로 시작 합니다.
  
2. 처음으로 (또는 구성 하기 전에) 원격 도구를 시작 하면, **원격 디버깅 구성** 대화 상자가 나타납니다.  
  
    ![RemoteDebuggerConfWizardPage](../media/remotedebuggerconfwizardpage.png "RemoteDebuggerConfWizardPage")  
  
3. Windows 서비스 API (발생 하는 Windows Server 2008 R2에만) 설치 하지 않은 경우 선택 합니다 **설치** 단추입니다.  
  
4. 원격 도구를 사용하려는 네트워크 종류를 선택합니다. 하나 이상의 네트워크 형식을 선택해야 합니다. 컴퓨터가 도메인을 통해 연결된 경우 첫 번째 항목을 선택해야 합니다. 컴퓨터가 작업 그룹 또는 홈 그룹을 통해 연결된 경우 두 번째 또는 세 번째 항목을 적절하게 선택해야 합니다.  
  
5. 선택할 **원격 디버깅 구성** 방화벽을 구성 하 고 도구를 시작 합니다.  
  
6. 구성이 완료되면 원격 디버거 창이 나타납니다.
  
    ![RemoteDebuggerWindow](../media/remotedebuggerwindow.png "RemoteDebuggerWindow")
  
    원격 디버거 연결 대기 중 이제입니다. 서버 이름의 기록해 두고이 나중에 Visual Studio에서 사용 하는 구성에 일치 해야 하기 때문에 포트 표시 되는 번호입니다.  
  
   디버깅 및 원격 디버거를 중지 해야 할 경우 완료 되 면 클릭 **파일 > 종료** 창에서. 다시 시작할 수 있습니다 합니다 **시작** 메뉴 또는 명령줄에서:  
  
   **\<원격 디버거 설치 디렉터리 >\\< x86, x64, ARM, ARM64, 또는 Appx > \msvsmon.exe**합니다.  
