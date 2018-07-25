---
title: 디버그 및 릴리스 구성 설정 | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2017
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.builds
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- configurations, release
- build configurations, release
- projects [Visual Studio], release configurations
- debugging [Visual Studio], release configurations
- release builds, changing settings
- debug builds
- debug builds, switching to release build
- debug builds, changing configuration settings
- debugging [Visual Studio], debug configurations
- projects [Visual Studio], debug configurations
- build configurations, debug
- debug configurations
- release builds, switching to debug build
- Visual Basic projects, debug and release builds
ms.assetid: 57b6bbb7-f2af-48f7-8773-127d75034ed2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ea27fdccaadc70f22d9c9c02d75ddef98a11be13
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153100"
---
# <a name="set-debug-and-release-configurations-in-visual-studio"></a>디버그 및 릴리스 구성에 Visual Studio 설정
Visual Studio 프로젝트에는 사용하는 프로그램에 대한 별도의 릴리스 및 디버그 구성이 있습니다. 이름이 의미하는 것처럼 디버그 버전은 디버깅용으로 빌드하고 릴리스 버전은 최종 릴리스 배포용으로 빌드합니다.  
  
프로그램의 디버그 구성은 완전히 기호화된 디버그 정보를 사용하여 컴파일되며 최적화되지 않습니다. 최적화하면 소스 코드와 생성된 명령 간의 관계가 복잡해지므로 디버깅이 복잡해집니다.  
  
프로그램의 릴리스 구성은 완전히 최적화되고, 기호화된 디버그 정보를 포함하지 않습니다. 디버그 정보가.pdb 파일을 생성할 수 있습니다 [컴파일러 옵션에 따라](#BKMK_symbols_release) 사용 되는 합니다. .Pdb 파일을 만드는 나중에 릴리스 버전을 디버깅 해야 할 경우에 매우 유용할 수 있습니다.  
  
빌드 구성에 대한 자세한 내용은 [빌드 구성 이해](../ide/understanding-build-configurations.md)를 참조하세요.  
  
빌드 구성을 변경할 수 있습니다 합니다 **빌드** 메뉴, 도구 모음에서 또는 프로젝트의 속성 페이지. 프로젝트 속성 페이지는 언어마다 다릅니다. 다음 절차는 메뉴 및 도구 모음에서 빌드 구성을 변경하는 방법을 보여 줍니다. 다른 언어의 프로젝트에서 빌드 구성을 변경 하는 방법에 대 한 자세한 내용은 아래 참고 항목 섹션을 참조 하세요.  
  
## <a name="change-the-build-configuration"></a>빌드 구성을 변경합니다  
  
1.  **빌드** 메뉴에서 **Configuration Manager**을 선택한 후 **디버그** 또는 **릴리스**합니다.  
  
2.  도구 모음에서 선택 하거나 **디버그** 또는 **릴리스** 에서 합니다 **솔루션 구성** 목록 상자입니다.  
  
     ![도구 모음 빌드 구성을](../debugger/media/toolbarbuildconfiguration.png "ToolbarBuildConfiguration")  
  
     이 도구 모음은 Express Edition에서 사용할 수 없습니다. 사용할 수는 **솔루션 빌드 F6** 하 고 **디버깅 시작 F5** 구성을 선택 하는 메뉴 항목입니다.

## <a name="BKMK_symbols_release"></a>빌드에 대 한 기호 (.pdb) 파일 생성

대부분의 프로젝트 형식에 대 한.pdb 파일 모두 디버그에 대해 기본적으로 생성 되 고 릴리스 빌드, 하지만 기본 설정을 특정 프로젝트 형식 및 Visual Studio 버전에 따라 다릅니다. 구성할 수 있습니다 컴파일러에서.pdb 파일을 생성 하는 여부 및 어떤 종류의 디버그 정보를 포함 합니다.

> [!IMPORTANT] 
> 디버거는 실행 파일을 빌드할 때 만든 .pdb 파일과 정확히 일치하는 실행 파일의 .pdb 파일만 로드합니다. 즉, .pdb는 원본이거나 원본 .pdb 파일의 복사본이어야 합니다. 자세한 내용은 [Why does Visual Studio require debugger symbol files to exactly match the binary files that they were built with?](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)

각 프로젝트 형식에는 이러한 옵션을 설정 하는 다른 방식으로 있을 수 있습니다.

### <a name="generate-symbol-files-for-a-c-aspnet-or-visual-basic-project"></a>C#, ASP.NET 또는 Visual Basic 프로젝트에 대 한 기호 파일을 생성 합니다.

C# 디버그 구성에 대 한 프로젝트 설정에 대 한 자세한 내용은 참조 하세요. [C# 디버그 구성에 대 한 설정을 프로젝트](../debugger/project-settings-for-csharp-debug-configurations.md)합니다. Visual basic의 경우 참조 [이 항목에서는](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)합니다.

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.

2. 선택 된 **릴리스** 또는 **디버그** 에서 빌드를 **구성** 목록.

2. 선택 **빌드** 설정과 클릭 합니다 **고급** 단추입니다.

    Visual basic의 경우 선택 합니다 **컴파일** 설정 및 **고급 컴파일 옵션** 대신 단추입니다.

3. 선택 **전체**, **휴대용**, 또는 **pdb_only** 에 **디버깅 정보** 목록 상자 (**디버그정보생성** Visual basic에서).

    이식 가능한 형식에는.NET Core에 대 한 최신 크로스 플랫폼 형식이입니다. 옵션에 대 한 자세한 내용은 참조 하세요. [고급 빌드 설정 대화 상자 (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md)합니다.

    ![C#에서 빌드에 대 한 Pdb를 생성](../debugger/media/dbg_project_properties_pdb_csharp.png "GeneratePDBsForCSharp")

4. 프로젝트를 빌드합니다.

    기호 파일이 실행 파일이 나 주 출력 파일과 동일한 폴더에 생성 합니다.

### <a name="generate-symbol-files-for-a-c-project"></a>C + + 프로젝트에 대 한 기호 파일을 생성 합니다.

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.

2. 선택 된 **릴리스** 또는 **디버그** 에서 빌드를 **구성** 목록.

2. 아래 **링커 > 디버깅**, 선택에 대 한 옵션을 원하는 **디버그 정보 생성**합니다.

    C + +에서 디버그 구성에 대 한 프로젝트 설정에 대 한 자세한 내용은 참조 하세요. [프로젝트는 c + + 디버그 구성에 대 한 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)합니다.

4. 프로그램 데이터베이스 파일 생성에 대 한 옵션 구성

    기본값은 대부분의 c + + 프로젝트에서 `$(OutDir)$(TargetName).pdb`,.pdb 파일의 출력 폴더에 생성 합니다.

    ![C + +에서 빌드에 대 한 Pdb를 생성](../debugger/media/dbg_project_properties_pdb_cplusplus.png "GeneratePDBsforCPlusPlus") 

5. 프로젝트를 빌드합니다.

    기호 파일이 실행 파일이 나 주 출력 파일과 동일한 폴더에 생성 합니다.
  
## <a name="see-also"></a>참고 항목  
 [고 Studio 디버거에서 기호 (.pdb) 파일 및 소스 파일 지정](../debugger/debugger-settings-and-preparation.md)  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)   
 [C + + 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [C# 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic 디버그 구성을 위한 프로젝트 설정](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)
