---
title: 원격 디버깅용 Windows 방화벽 구성 | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 66e3230a-d195-4473-bbce-8ca198516014
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9688948ebe2fa5e045578ee808e068d59450d748
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433393"
---
# <a name="configure-the-windows-firewall-for-remote-debugging"></a>원격 디버깅을 위해 Windows 방화벽 구성
이 항목에서는 다음 운영 체제를 실행하는 컴퓨터에서 원격 디버깅을 사용하도록 방화벽을 구성하는 방법을 설명합니다.  
  
-   Windows 10  
  
-   Windows 8/8.1  
  
-   Windows 7   
  
-   Windows Server 2012 R2  

-   Windows Server 2012
  
-   Windows Server 2008 R2 
  
 디버그 중인 네트워크가 방화벽으로 보호되지 않는 경우에는 이 구성이 필요하지 않습니다. 그렇지 않은 경우 Visual Studio를 호스트하는 컴퓨터와 디버그해야 하는 원격 컴퓨터 둘 다에서 방화벽 구성을 변경해야 합니다.  
  
 **IPSec** 네트워크에서 IPSec을 사용하여 통신을 수행해야 하는 경우 Visual Studio 호스트 컴퓨터와 원격 컴퓨터 둘 다에서 추가 포트를 열어야 합니다.  
  
 **웹 서버** 원격 웹 서버를 디버그하는 경우 원격 컴퓨터에서 추가 포트를 열어야 합니다. (IIS에 대 한 포트 80 열려 있어야 합니다.)  
  
 두 컴퓨터에서 동일한 운영 체제를 실행할 필요는 없습니다. 예를 들어 Visual Studio 컴퓨터는 Windows 10을 실행하고 원격 컴퓨터는 Windows Server 2012 R2를 실행할 수 있습니다.      
  
## <a name="ports-on-the-remote-computer-that-enable-remote-debugging"></a>원격 디버깅을 사용할 수 있도록 하는 원격 컴퓨터의 포트  
  
|**포트**|**들어오는/나가는 포트**|**프로토콜**|**설명**|   
|-|-|-|-|  
|4022|들어오|TCP|VS 2017. 포트 번호는 각 Visual Studio 버전마다 2씩 증가합니다. 자세한 내용은 [Visual Studio 원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)합니다.|  
|4023|들어오|TCP|VS 2017. 포트 번호는 각 Visual Studio 버전마다 2씩 증가합니다. (만 원격으로 사용 되는 디버그 원격 디버거의 64 비트 버전에서 32 비트 프로세스입니다.) 자세한 내용은 [Visual Studio 원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)합니다.| 
|3702|나가는 포트|UDP|(선택 사항) 원격 디버거 검색에 필요합니다.|    
  
## <a name="how-to-configure-ports-in-windows-firewall"></a>Windows 방화벽에서 포트를 구성하는 방법  

원격 디버거를 사용 하거나 Visual Studio를 설치할 때 소프트웨어는 올바른 포트를 열어야 하려고 합니다. 그러나 일부 시나리오 (예: 타사 방화벽을 사용 하 여) 수동으로 포트를 열기 해야 합니다. 포트가 열려 있는지 확인 해야 할 경우 참조 [문제 해결](#troubleshooting)합니다. 포트 열기에 대 한 지침을 이전 버전의 Windows에서 달라질 수 있습니다.

포트를 열려면:
  
1. 엽니다는 **시작** 메뉴에서 검색 **Windows Firewall with Advanced Security**합니다.

2. 선택한 **인바운드 규칙 > 새 규칙 > 포트**를 클릭 하 고 **다음**합니다. (보내는 규칙을 선택할 **아웃 바운드 규칙** 대신 합니다.)

3. 선택할 **TCP** 하거나 **UDP**포트 번호에 따라 합니다.

4. 아래 **특정 로컬 포트**포트 번호를 입력, 클릭 **다음**합니다.

5. 클릭 **연결 허용** 을 클릭 한 다음 **다음**합니다.

6. 하나 이상의 네트워크 형식을 선택 포트에 대해 사용 하도록 설정 하 고 클릭 **다음**합니다.

    선택한 유형은 원격 컴퓨터가 연결된 네트워크를 포함해야 합니다.
7. 이름을 추가 합니다 (예를 들어 **msvsmon**, **IIS**, 또는 **Web Deploy**) 규칙을 클릭 **마침**.

    규칙이 인바운드 또는 아웃 바운드 규칙 목록에 새 규칙이 표시 됩니다.

## <a name="troubleshooting"></a>문제 해결

원격 디버거를 사용 하 여 앱에 연결 하는 데 문제가 있는 경우에 올바른 포트가 열려 있는지 확인 해야 합니다.

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-visual-studio-computer"></a>포트가 Visual Studio 컴퓨터에서 Windows 방화벽에서 열려 있는지 확인 합니다.  
 Windows 방화벽을 구성하기 위한 지침은 운영 체제마다 약간 다릅니다. Windows 8/8.1, Windows 10 및 Windows Server 2012, 단어 **앱** 사용 될 Windows 7 또는 Windows Server 2008, 단어 **프로그램** 사용 됩니다.  다음 단계를 사용 하 여 단어 **앱**합니다.  
  
1.  Windows 방화벽 페이지를 엽니다. **시작** 메뉴 검색 상자에 **Windows 방화벽**을 입력합니다.  
  
2.  **Windows 방화벽을 통해 앱 또는 기능 허용**을 클릭합니다.  
  
3.  **허용된 앱 및 기능** 목록에서 **Visual Studio 원격 디버거 검색**을 찾습니다. 표시되는 경우 선택되었으며 하나 이상의 네트워크 종류도 선택되었는지 확인합니다.  
  
4.  **Visual Studio 원격 디버거 검색** 이 표시되지 않는 경우 **다른 앱 허용**을 클릭합니다. 여전히 표시 되지 않는 경우에 **앱 추가** 창에서 클릭 **찾아보기** 이동한  **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Remote디버거**. 응용 프로그램에 대한 적절한 폴더(x86, x64, Appx)를 찾은 다음 **msvsmon.exe**를 선택합니다. **추가**를 클릭합니다.  
  
5.  에 **허용 된 앱 및 기능** 목록에서 **Visual Studio 원격 디버거**합니다. 원격 디버깅 모니터에서 통신하려는 네트워크 종류(**도메인, 홈/회사(개인), 공용**)를 하나 이상 선택합니다. 종류는 Visual Studio 컴퓨터가 연결된 네트워크를 포함해야 합니다. 

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-remote-computer"></a>포트는 원격 컴퓨터에서 Windows 방화벽에서 열려 있는지 확인  
 원격 디버깅 구성 요소는 원격 컴퓨터에 설치하거나 공유 디렉터리에서 실행할 수 있습니다. 두 경우 모두 원격 컴퓨터의 방화벽을 구성해야 합니다. 원격 디버깅 구성 요소는 다음 위치에 있습니다.  
  
 **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Remote 디버거**  
  
 Windows 방화벽을 구성하기 위한 지침은 운영 체제마다 약간 다릅니다. Windows 8/8.1, Windows 10 및 Windows Server 2012, 단어 **앱** 사용 될 Windows 7 또는 Windows Server 2008, 단어 **프로그램** 사용 됩니다.  다음 단계를 사용 하 여 단어 **앱**합니다.  
  
1.  Windows 방화벽 페이지를 엽니다. **시작** 메뉴 검색 상자에 **Windows 방화벽**을 입력합니다.  
  
2.  **Windows 방화벽을 통해 앱 또는 기능 허용**을 클릭합니다.  
  
3.  에 **허용 된 앱 및 기능** 목록에서 검색할 **Visual Studio 원격 디버거**합니다. 표시되는 경우 선택되었으며 하나 이상의 네트워크 종류도 선택되었는지 확인합니다.  
  
4.  하는 경우 **Visual Studio 원격 디버거** 는 클릭 나열 되지 **다른 앱 허용**합니다. 여전히 표시 되지 않는 경우에 **추가 된 앱 창의**, 클릭 **찾아보기** 이동한  **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Remote디버거**. 응용 프로그램에 대한 적절한 폴더(x86, x64, Appx)를 찾은 다음 **msvsmon.exe**를 선택합니다. **추가**를 클릭합니다.  
  
5.  에 **허용 된 앱** 목록에서 **Visual Studio 원격 디버거**합니다. 원격 디버깅 모니터에서 통신하려는 네트워크 종류(**도메인, 홈/회사(개인), 공용**)를 하나 이상 선택합니다. 종류는 Visual Studio 컴퓨터가 연결된 네트워크를 포함해야 합니다. 

### <a name="managed-or-native-compatibility-mode-open-additional-ports-on-the-remote-computer"></a>(관리 또는 네이티브 호환성 모드) 원격 컴퓨터에서 추가 포트를 열려면

디버거에 대 한 호환성 모드를 사용 하는 경우 (**도구 > 옵션 > 디버깅**), 추가 포트를 열 수 해야 합니다. 호환성 모드를 사용 하면 레거시 버전의 디버거 및 다른 포트가 필요 합니다.

> [!NOTE]
> 레거시 디버거 버전이 Visual Studio 2010 디버거입니다.
  
|**포트**|**들어오는/나가는 포트**|**프로토콜**|**설명**|  
|-|-|-|-|  
|135, 139, 445|나가는 포트|TCP|필수.|  
|137, 138|나가는 포트|UDP|필수.|  
|500, 4500|나가는 포트|UDP|도메인 정책에 따라 IPSec을 통해 네트워크 통신을 수행해야 하는 경우에 필요합니다.|  
|80|나가는 포트|TCP|웹 서버 디버깅에 필요합니다.|
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅](../debugger/remote-debugging.md)