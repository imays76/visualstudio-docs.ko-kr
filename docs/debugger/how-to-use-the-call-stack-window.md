---
title: Visual Studio 디버거에서 호출 스택을 보려면 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/06/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.callstack
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
- aspx
helpviewer_keywords:
- threading [Visual Studio], displaying calls to or from
- functions [debugger], viewing code on call stack
- disassembly code
- breakpoints, Call Stack window
- debugging [Visual Studio], switching to another stack frame
- debugging [Visual Studio], Call Stack window
- Call Stack window, viewing source code for functions on the call stack
- stack, switching stack frames
- Call Stack window, viewing disassembly code for functions on the call stack
ms.assetid: 5154a2a1-4729-4dbb-b675-db611a72a731
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 168f89512dee8331448db1becabdc7262b5e4744
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43774735"
---
# <a name="view-the-call-stack-and-use-the-call-stack-window-in-the-visual-studio-debugger"></a>호출 스택 보기 및 Visual Studio 디버거에서 호출 스택 창 사용

사용 하 여 합니다 **호출 스택** 창에서 현재 스택에 있는 함수 또는 프로시저 호출을 볼 수 있습니다. 합니다 **호출 스택** 창 있는 메서드 및 함수는 호출 되는 순서를 보여 줍니다. 호출 스택은 좋은 점검 하 여 앱의 실행 흐름을 이해 합니다.
  
때 [디버깅 기호](#bkmk_symbols) 호출 스택의 일부에 대해 사용할 수 없는 합니다 **호출 스택** 창 수 호출 스택의 해당 부분에 대 한 올바른 정보를 표시할 수 없습니다. 발생 하는 경우에 다음과 같이 출력이 됩니다.  
  
`[Frames below may be incorrect and/or missing, no symbols loaded for name.dll]`

>  [!NOTE]
> 합니다 **호출 스택** Eclipse와 같은 일부 Ide 창에 디버그 관점 비슷합니다. 

> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 여기서 설명하는 것과 다를 수 있습니다. 설정을 변경 하려면 선택 **설정 가져오기 및 내보내기** 에 **도구** 메뉴.  참조 [IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)
  
## <a name="view-the-call-stack-while-in-the-debugger"></a>디버거 내에서 호출 스택을 보려면 
  
-   디버깅 하는 동안 합니다 **디버그** 메뉴에서 **Windows > 호출 스택**합니다.

 ![호출 스택 창](../debugger/media/dbg_basics_callstack_window.png "CallStackWindow")

노란색 화살표는 현재 실행 포인터가 있는 스택 프레임을 나타냅니다. 기본적으로이 원본에 해당 정보가 표시 되는 스택 프레임 **지역**를 **자동**합니다 **조사식**, 및 **디스어셈블리** windows . 디버거 컨텍스트 스택의 다른 프레임으로 변경 하려는 경우 수 이렇게 [다른 스택 프레임으로 전환](#bkmk_switch)합니다.   
  
## <a name="display-non-user-code-in-the-call-stack-window"></a>사용자 코드가 아닌 호출 스택 창에 표시  
  
-   마우스 오른쪽 단추로 클릭 합니다 **호출 스택** 창과 선택 **외부 코드 포시**합니다.

사용자 이외의 경우 표시 되지 않는 모든 코드가 됩니다 [Just My Code](../debugger/just-my-code.md) 사용 가능 합니다. 관리 코드에서 사용자 코드가 아닌 프레임 기본적으로 숨겨집니다. 사용자 코드가 아닌 프레임 대신 다음과 같이 출력 표시 됩니다.  
  
**[\<외부 코드 >]**  
  
## <a name="bkmk_switch"></a> 다른 스택 프레임 (디버거 컨텍스트 변경)으로 전환
  
1.  에 **호출 스택** 창, 코드와 확인 하려는 데이터가 포함 된 스택 프레임 마우스 오른쪽 단추로 클릭 합니다.

    또는 프레임을 두 번 클릭 수를 **호출 스택** 창에 선택한 프레임으로 전환 합니다. 
  
2.  선택 **프레임으로 전환**합니다.  
  
     선택한 스택 프레임 옆에 끝이 굽은 녹색 화살표가 표시 됩니다. 실행 포인터는 여전히 노란색 화살표로 표시되어 있는 원래 프레임에 그대로 있습니다. 선택 하는 경우 **단계** 또는 **계속** 에서 합니다 **디버그** 선택한 프레임이 아닌, 메뉴, 원래 프레임에서 실행이 계속 됩니다.  
  
## <a name="view-the-source-code-for-a-function-on-the-call-stack"></a>호출 스택에 있는 함수의 소스 코드 보기  
  
-   에 **호출 스택** 창, 소스 코드를 보려는 함수를 보고 선택 하려면 마우스 오른쪽 단추로 클릭 **소스 코드로 이동**합니다.

## <a name="run-to-a-specific-function-from-the-call-stack-window"></a>호출 스택 창에서 특정 함수까지 실행  
  
-  에 **호출 스택** 함수를 선택, 마우스 오른쪽 단추로 클릭 및 선택 창 **커서까지 실행**합니다.  
  
## <a name="set-a-breakpoint-on-the-exit-point-of-a-function-call"></a>함수 호출의 종료 지점에 중단점을 설정 합니다.  
  
-   참조 [호출 스택 함수에 중단점을 설정](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_the_call_stack_window)합니다.

## <a name="display-calls-to-or-from-another-thread"></a>나 다른 스레드로 호출 표시  
  
-   마우스 오른쪽 단추로 클릭 합니다 **호출 스택** 창과 선택 **다른 스레드로 호출 / 다른 스레드에서 호출 포함**합니다.   
  
## <a name="visually-trace-the-call-stack"></a>호출 스택을 시각적으로 추적  

Visual Studio Enterprise (전용)를 사용 하는 경우에 디버깅 하는 동안 호출 스택에 대해 코드 맵을 볼 수 있습니다.

- 에 **호출 스택** 창 바로 가기 메뉴를 엽니다. 선택할 **호출 스택 코드 맵에 표시**합니다. (키보드: **CTRL** + **SHIFT** + **`**)  
  
    자세한 내용은 [디버깅 하는 동안 호출 스택의 메서드 매핑](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)합니다.

![코드 맵에 호출 스택 표시](../debugger/media/dbg_basics_show_call_stack_on_code_map.gif "ShowCallStackOnCodeMap")
  
## <a name="view-the-disassembly-code-for-a-function-on-the-call-stack"></a>호출 스택에 있는 함수의 디스어셈블리 코드 보기  
  
-   에 **호출 스택** 창에서 디스어셈블리 코드를 보려는 함수를 보고 선택 하려면 마우스 오른쪽 단추로 클릭 **디스어셈블리로 이동**합니다.    

## <a name="change-the-optional-information-displayed"></a>표시 되는 선택적 정보를 변경 합니다.  
  
-   마우스 오른쪽 단추로 클릭 합니다 **호출 스택** 창 및 설정 하거나 해제 **표시 \<**  _정보를_ **>**.  
  
## <a name="bkmk_symbols"></a> 모듈에 대 한 기호 로드
에 **호출 스택** 창 디버깅 기호가 로드 현재 없는 코드에 대 한 기호를 로드할 수 있습니다. 이러한 기호는 Microsoft 공용 기호 서버에서 다운로드한 .NET Framework 또는 시스템 기호일 수도 있고 디버깅 중인 컴퓨터의 기호 경로에 있는 기호일 수도 있습니다.  
  
참조 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
### <a name="to-load-symbols"></a>기호를 로드하려면  
  
1.  에 **호출 스택** 창을 오른쪽 단추로 클릭 하는 기호에 대 한 스택 프레임을 로드 하지 않습니다. 프레임이 흐리게 표시됩니다.  
  
2.  가리킨 **기호 로드** 클릭 하 고 **Microsoft 기호 서버** (있는 경우) 하거나 기호 경로 찾습니다.  
  
### <a name="to-set-the-symbol-path"></a>기호 경로를 설정하려면  
  
1.  에 **호출 스택** 창에서 선택 **기호 설정** 바로 가기 메뉴에서.  
  
     합니다 **옵션** 대화 상자가 열립니다 하며 **기호** 페이지가 표시 됩니다.  
  
2.  클릭 **기호 설정**합니다.  
  
3.  에 **옵션** 대화 상자에서 폴더 아이콘을 클릭 합니다.  
  
     에 **기호 파일 (.pdb) 위치** 상자에 커서가 표시 됩니다.  
  
4.  디버깅 중인 컴퓨터의 기호 위치에 대한 디렉터리 경로 이름을 입력합니다. 로컬 및 원격 디버깅을 위해 로컬 컴퓨터의 경로입니다.
  
5.  **확인**을 클릭하여 **옵션** 대화 상자를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 스택 창의 혼합 코드 및 누락된 정보](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [중단점 사용](../debugger/using-breakpoints.md)