---
title: '방법: IIS 속성 설정 확인 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- IIS, property settings
- debugging Web applications, troubleshooting
- IIS administration tool
- Web applications, setting properties
- properties [debugger], setting with IIS administration tool
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6eb30c411b7a863d4ba9522159d6100abb48cb6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49884851"
---
# <a name="how-to-verify-iis-property-settings"></a>방법: IIS 속성 설정 확인
IIS 관리 도구를 사용하여 웹 응용 프로그램의 속성을 설정할 수 있습니다. 이러한 속성이 제대로 설정되어 있어야 응용 프로그램이 실행되므로 일반적으로 문제를 해결하는 데는 이러한 설정을 확인하는 단계가 필요합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-check-iis-settings-for-the-web-application"></a>웹 응용 프로그램에 대한 IIS 설정을 확인하려면  
  
1. 열기는 **관리 도구** 창:에 **시작** 메뉴에서 **프로그램**를 클릭 하 고 **관리 도구**합니다. 경우 **관리 도구** 에 나타나지 않습니다 합니다 **프로그램** 메뉴를 클릭 한 다음에서 찾습니다 합니다 **제어판**합니다.  
  
   -   Windows 2000에서 선택 **인터넷 서비스 관리자**합니다.  
  
   -   Windows XP에서 선택 **인터넷 정보 서비스**합니다.  
  
   -   Windows Server 2003에서 두 번 클릭 **서버 관리**합니다.  
  
        합니다 **서버 관리** 창이 열립니다. 아래 **응용 프로그램 서버**, 클릭 **응용 프로그램 서버 관리**합니다.  
  
        합니다 **응용 프로그램 서버** 창이 열립니다. 엽니다는 **인터넷 정보 서비스 (IIS) 관리자** 왼쪽된 창에서 노드.  
  
2. 대화 상자에서 현재 컴퓨터의 트리 컨트롤 노드를 클릭합니다. 클릭 합니다 **웹 사이트** 노드를 웹 응용 프로그램의 노드를 선택 합니다. 웹 사이트 노드를 이므로의 형제 일은 **기본 웹 사이트** 노드 또는 기존 웹 사이트 노드 아래에 있는 가상 디렉터리 노드일 합니다.  
  
3. 웹 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 클릭 **속성**합니다.  
  
4. 웹 응용 프로그램에 대한 보안 설정을 확인합니다.  
  
   1.  웹 응용 프로그램에서 **속성** 창에서 클릭 합니다 **디렉터리 보안** 탭을 클릭 **편집**합니다.  
  
   2.  에 **인증 방법** 대화 상자에서 **익명 액세스 가능** 하 고 **통합 Windows 인증** 이미 선택 되어 있지 않은 경우.  
  
   3.  클릭 **확인** 닫으려면 합니다 **인증 방법을** 대화 상자.  
  
5. ATL 서버 응용 프로그램의 경우 DEBUG 동사가 ISAPI 확장과 관련이 있는지 여부를 확인합니다. 자세한 내용은 [방법: 확장을 사용 하 여 디버그 동사 연결](https://msdn.microsoft.com/library/50d261d3-4bd4-41c0-b44e-3591086f121e)합니다.  
  
6. 에 대 한는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램을 하는지 확인 한 가상 폴더 응용 프로그램에서 설정 된 응용 프로그램 이름이 **인터넷 정보 서비스 (IIS) 관리자**를 **인터넷 서비스 관리자** 또는 **인터넷 정보 서비스**합니다.  
  
   1.  웹 응용 프로그램에서 **속성** 창에서 합니다 **디렉터리** 가상 디렉터리에서 응용 프로그램은 탭 또는 **홈 디렉터리** 응용 프로그램 탭 웹 사이트입니다.  
  
   2.  확인의 이름과 **로컬 경로** 응용 프로그램이 실제로 배포 된 디렉터리의 이름과 일치 합니다.  
  
   3.  아래 **응용 프로그램 설정**, 응용 프로그램을 포함 하는 루트 디렉터리의 이름을 입력 합니다.  
  
   4.  클릭 **확인** 닫으려면 합니다 **속성** 대화 상자.  
  
7. 에 대 한는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램을 클릭 합니다 **ASP.NET** 탭을 확인 하는 올바른 버전의 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 지정 된.  
  
8. 클릭 **확인** 닫으려면 합니다 **속성** 대화 상자.  
  
9. 클릭 **확인** 닫으려면 합니다 **인터넷 정보 서비스 (IIS) 관리자**를 **인터넷 서비스 관리자**, 또는 **인터넷 정보 서비스**대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [문제 해결](../debugger/debugging-web-applications-troubleshooting.md)