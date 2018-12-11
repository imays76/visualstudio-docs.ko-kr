---
title: '오류: 통합된 Windows 인증을 사용 하지 않기 때문에 실패 디버깅 | Microsoft Docs'
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
- vs.debug.error.webdbg_ntlm_authn_not_enabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 6027cd94-74cf-470f-b7ce-6f6b68bc56ba
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0b922e8e8fde8b185207810d107afb9a9c5a6e05
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51757254"
---
# <a name="error-debugging-failed-because-integrated-windows-authentication-is-not-enabled"></a>오류: Windows 통합 인증을 사용할 수 없기 때문에 디버깅을 하지 못했습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

인증 오류로 인해 디버깅을 요청한 사용자를 인증할 수 없습니다. 웹 응용 프로그램 또는 XML Web services를 한 단계씩 실행하려고 할 때 이 오류가 발생할 수 있습니다. 이 오류는 Windows 통합 인증이 사용할 수 없도록 설정되어 있기 때문에 발생할 수 있습니다. 이 인증을 사용하려면 "통합 Windows 인증을 사용하려면"의 단계를 따릅니다.  
  
 통합된 Windows 인증을 사용 하도록 설정한 경우이 오류가 계속 나타나면 있기 때문에이 오류는 발생 **Windows 도메인 서버의 다이제스트 인증** 사용 가능 합니다. 이 경우에는 네트워크 관리자에게 문의하십시오.  
  
### <a name="to-enable-integrated-windows-authentication"></a>Windows 통합 인증을 사용하려면  
  
1.  관리자 계정을 사용하여 웹 서버에 로그온합니다.  
  
2.  클릭 **시작** 을 클릭 한 다음 **제어판**합니다.  
  
3.  **Control Panel**를 두 번 클릭 **관리 도구**합니다.  
  
4.  두 번 클릭 **인터넷 정보 서비스**합니다.  
  
5.  웹 서버 노드를 클릭합니다.  
  
     A **웹 사이트** 서버 이름 아래에 폴더가 열립니다.  
  
6.  모든 웹 사이트 또는 개별 웹 사이트에 대해 인증을 구성할 수 있습니다. 모든 웹 사이트에 대 한 인증을 구성 하려면 마우스 오른쪽 단추로 클릭 합니다 **웹 사이트** 폴더 및 클릭 **속성**합니다. 개별 웹 사이트에 대 한 인증을 구성 하려면 엽니다는 **웹 사이트** 폴더, 개별 웹 사이트를 마우스 오른쪽 단추로 클릭 **속성**합니다.  
  
     합니다 **속성** 대화 상자가 표시 됩니다.  
  
7.  클릭 합니다 **디렉터리 보안** 탭 합니다.  
  
8.  에 **익명 액세스 및 인증 제어** 섹션에서 클릭 **편집**합니다.  
  
     합니다 **인증 방법을** 대화 상자가 표시 됩니다.  
  
9. 아래 **인증 된 액세스**를 선택 **통합 Windows 인증**합니다.  
  
10. 클릭 **확인** 닫으려면 합니다 **인증 방법을** 대화 상자.  
  
11. 클릭 **확인** 닫으려면 합니다 **속성** 대화 상자.  
  
12. 닫기 합니다 **인터넷 정보 서비스** 창입니다.  
  
### <a name="to-enable-integrated-windows-authentication-in-windows-vistaiis-7"></a>Windows Vista/IIS 7에서 통합 Windows 인증을 사용하려면  
  
1.  관리자 계정을 사용하여 웹 서버에 로그온합니다.  
  
2.  Windows 인증 및 II6 관리 호환성을 설정하지 않은 경우 다음 단계에 따라 이를 설정합니다.  
  
    1.  클릭 **시작**, 클릭 **제어판** 을 클릭 한 다음 **프로그램**합니다.  
  
    2.  아래 **프로그램 및 기능**, 클릭 **설정 하는 Windows 기능 사용 /** 합니다.  
  
         사용자 Access Control 대화 상자가 표시되고 작업을 계속할 수 있는 권한이 있는지 묻습니다.  
  
    3.  **Continue(계속)** 를 클릭합니다.  
  
         Windows 기능 대화 상자가 표시됩니다.  
  
    4.  기능 목록에서를 확장 합니다 **인터넷 정보 서비스** 노드.  
  
    5.  아래 **인터넷 정보 서비스**를 확장 합니다 **World Wide Web 서비스** 노드.  
  
    6.  아래 **World Wide Web 서비스**, 클릭 **보안**합니다.  
  
    7.  클릭 **Windows 인증**합니다.  
  
    8.  아래 **인터넷 정보 서비스**를 확장 합니다 **웹 관리 도구** 노드.  
  
    9. 아래 **웹 관리 도구**를 확장 합니다 **IIS 6 관리 호환성** 노드를 선택한는 **IIS 6 메타 베이스 및 IIS 6 구성 호환성** 확인란 합니다.  
  
    10. 아래 **웹 관리 도구**를 선택 **IIS 관리 콘솔** 를 클릭 하 고 **확인 합니다.**  
  
    11. 컴퓨터를 다시 시작하여 이러한 변경 내용을 적용합니다.  
  
3.  클릭 **시작** 을 클릭 하 고 **제어판**합니다.  
  
4.  클릭 **클래식 보기**를 차례로 클릭 한 다음 **관리 도구**합니다.  
  
5.  에 **이름을** 열과 두 번 클릭 **인터넷 정보 서비스 (IIS) 관리자**합니다.  
  
6.  에 **연결** 열에서 서버 노드를 확장 합니다.  
  
     A **웹 사이트** 서버 이름 아래에 폴더가 열립니다.  
  
7.  확장 된 **웹 사이트** 노드 통합된 Windows 인증을 사용 하려는 웹 사이트를 클릭 합니다.  
  
8.  가운데 창의 제목이 선택한 웹 사이트의 이름으로 변경됩니다. 이 창에서 아래 합니다 **IIS** 머리글을 두 번 클릭 **인증**합니다.  
  
     창의 제목이 **인증**합니다.  
  
9. 에 **인증** 창에서를 **이름** 열을 마우스 오른쪽 단추로 클릭 **Windows 인증** 클릭 하 고 **사용 하도록 설정**.  
  
10. 닫기 합니다 **인터넷 정보 서비스 (IIS) 관리자** 창입니다.  
  
## <a name="see-also"></a>참고 항목  
 [웹 응용 프로그램 디버깅: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)   
 [Microsoft 다이제스트 인증](http://go.microsoft.com/fwlink/?LinkId=77938)   
 [IIS 7.0 사용 하 여 Windows Vista에서 웹 응용 프로그램 및 Visual Studio를 실행합니다.](http://msdn.microsoft.com/library/262a82ac-dd0e-4096-86c6-fb463e88be66)



