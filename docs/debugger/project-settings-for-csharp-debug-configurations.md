---
title: C# 디버그 구성에 대 한 설정을 프로젝트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debug configurations, C#
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debugging [C#], debugger settings
ms.assetid: e30ca810-66e9-4d6e-9cf6-9f285cd0b100
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a65928e8a5a734e84d51cbb4368c7346ba8c2edb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49896343"
---
# <a name="project-settings-for--c-debug-configurations"></a>C# 디버그 구성에 대한 프로젝트 설정
C# 디버그 구성에 대 한 프로젝트 설정을 변경할 수 있습니다 합니다 **속성 페이지** 창에 설명 된 대로 [디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)합니다. 다음 표에에서 디버거 관련 설정을 확인할 수 있는 위치를 표시 합니다 **속성 페이지** 창입니다.  
  
> [!WARNING]
>  이 항목은 UWP 앱에 적용되지 않습니다. 참조 [(VB, C#, c + + 및 XAML) 디버그 세션 시작](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_Debug_tab"></a> 디버그 탭  
  
| **설정** | **설명** |
|-------------------------------------| - |
| **구성** | 응용 프로그램의 컴파일 모드를 설정합니다. 중에서 선택 **활성 (디버그)**, **디버그**를 **릴리스**, **구성을 모두**합니다. |
| **시작 작업** | 이 컨트롤 그룹은 디버그 메뉴에서 시작을 선택할 때 수행되는 작업을 지정합니다.<br /><br /> -   **프로젝트 시작** 기본값이 며 디버깅에 대 한 시작 프로젝트를 시작 합니다. 자세한 내용은 [시작 프로젝트 선택](/previous-versions/visualstudio/visual-studio-2010/0s590bew(v=vs.100))합니다.<br />-   **시작 외부 프로그램** 시작 된 프로그램에 연결을 사용 하면 부분을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트입니다. 자세한 내용은 [실행 프로그램에 연결](/previous-versions/visualstudio/visual-studio-2010/c6wf8e4z(v=vs.100))합니다.<br />-   **URL로 브라우저 시작** 웹 응용 프로그램을 디버깅할 수 있도록 합니다. |
| **명령줄 인수** | 디버깅할 프로그램에 대한 명령줄 인수를 지정합니다. 명령 이름은 시작 외부 프로그램에 지정된 프로그램 이름입니다. 시작 작업이 시작 URL로 설정되면 명령줄 인수를 지정할 수 없습니다. |
| **작업 디렉터리** | 디버깅 중인 프로그램의 작업 디렉터리를 지정합니다. [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]에서는 응용 프로그램이 시작된 디렉터리가 작업 디렉터리입니다. 이 디렉터리는 기본적으로 \bin\debug입니다. |
| **원격 컴퓨터 사용** | 디버깅을 위해 응용 프로그램을 실행할 원격 컴퓨터의 이름을 요소나 [Msvsmon 서버 이름](../debugger/remote-debugging.md)합니다. 원격 컴퓨터에 있는 EXE의 위치는 구성 속성 폴더의 빌드 범주에 있는 출력 경로 속성으로 지정됩니다. 이 위치는 원격 컴퓨터의 공유할 수 있는 디렉터리여야 합니다. |
| **비관리 코드 디버깅 사용** | 관리되는 응용 프로그램에서의 비관리 네이티브 Win32 코드에 대한 호출을 디버깅할 수 있습니다. |
| **SQL Server 디버깅 사용** | SQL Server 데이터베이스 개체를 디버깅할 수 있습니다. |
  
##  <a name="BKMK_Build_tab"></a> 빌드 탭  
  
|설정|설명|  
|-------------|-----------------|  
|**조건부 컴파일 기호:**|DEBUG 및 TRACE 상수가 여기에 정의됩니다.<br /><br /> 이러한 상수의 조건부 컴파일을 사용 하도록 설정 합니다 [Debug 클래스](/dotnet/api/system.diagnostics.debug) 하 고 [Trace 클래스](/dotnet/api/system.diagnostics.trace)합니다. 이 상수를 정의 사용 하 여 디버그 및 Trace 클래스 메서드의 출력을 생성 합니다 [출력 창](../ide/reference/output-window.md)합니다. 이 상수를 정의하지 않으면 Debug 및 Trace 클래스 메서드가 컴파일되지 않으므로 결과가 생성되지 않습니다.<br /><br /> 일반적으로 디버그 프로그램의 디버그 버전에서 정의 되며 릴리스 버전에서 정의 합니다.<br />추적은 디버그 및 릴리스 버전에서는 일반적으로 정의 됩니다.|  
|**코드 최적화**|최적화된 코드에만 나타나는 버그가 발견되지 않을 경우, 디버그 버전에서 이 설정을 해제해야 합니다. 코드를 최적화하면 명령이 소스 창에 있는 문에 직접 대응되지 않기 때문에 디버깅하기 어렵습니다.|  
|**출력 경로:**|디버깅 작업에서는 일반적으로 bin\Debug로 설정합니다.|

> [!NOTE]
> 찾을 디버그 옵션에 대 한 자세한 내용은 합니다 **고급** 단추를 참조 하십시오 [고급 빌드 설정 대화 상자 (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md)합니다. 기호 (.pdb) 파일에 대 한 이식 가능한 형식에는.NET Core에 대 한 최신 크로스 플랫폼 형식이입니다. 
  
## <a name="see-also"></a>참고 항목  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)