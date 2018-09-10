---
title: 디버거에서 Dll 및 실행 파일을 보려면 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.modules
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, Modules window
- Modules window
- executable files, displaying while debugging
- debugging [Visual Studio], displaying modules
- DLLs, displaying while debugging
- modules, displaying
ms.assetid: d840fdca-b035-4452-b652-72580c831896
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f582c435239c83503b179d6bb5e142936a41cb4b
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279013"
---
# <a name="view-dlls-and-executables-using-the-modules-window-in-the-visual-studio-debugger"></a>Dll 및 Visual Studio 디버거에서 모듈 창을 사용 하 여 실행 파일을 보려면
 
합니다 **모듈** Dll 및 실행 파일 (EXE) 각각에 대 한 관련 정보를 표시 및 프로그램에서 사용 되는 창에 표시 합니다. 

> [!NOTE]
>  SQL 또는 스크립트 디버깅에는 이 기능을 사용할 수 없습니다. 
  
### <a name="to-display-the-modules-window"></a>모듈 창을 표시 하려면  
  
-   디버깅 하는 동안 선택 **디버그 > Windows** 을 클릭 한 다음 **모듈**합니다.  
  
     기본적으로 **모듈** 창에서는 모듈이 로드 순서 대로 정렬 합니다. 그러나 열을 기준으로 정렬할 수도 있습니다.  
  
### <a name="to-sort-by-any-column"></a>열별로 정렬하려면  
  
-   정렬 기준이 될 열 맨 위에 있는 단추를 클릭합니다.  
  
     기호를 로드 하거나 기호 경로 지정 합니다 **모듈** 바로 가기 메뉴를 사용 하 여 창입니다.  
  
## <a name="loading-symbols"></a>기호 로드  
 에 **모듈** 창 디버깅 기호가 로드 된 모듈을 볼 수 있습니다. 이 정보에 표시 된 **기호 상태** 열입니다. 상태 표시 되 면 **건너뜀 loadingCannot 찾거나 PDB 파일을 엽니다**, 또는 **포함/제외 설정으로 로드가 비활성화 되었습니다**, Microsoft 공용 기호에서 기호를 다운로드 하도록 디버거에 지시할 수 있습니다 서버 컴퓨터의 기호 경로에서 기호를 로드 합니다. 자세한 내용은 참조 하세요. [지정 기호 (.pdb) 및 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>기호를 수동으로 로드하려면  
  
1.  에 **모듈** 창에서 기호가 로드 되지 않은 모듈을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  가리킨 **에서 기호 로드** 클릭 하 고 **Microsoft 기호 서버** 하거나 **기호 경로**합니다.  
  
#### <a name="to-change-symbol-load-settings"></a>기호 로드 설정을 변경하려면  
  
1.  에 **모듈** 창에서 모든 모듈을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  클릭 **기호 설정**합니다.  
  
     에 설명 된 대로 이제 기호 로드 설정의 변경할 수 있습니다 [기호 위치를 지정 하 고 로드 동작](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior)합니다. 디버깅 세션을 다시 시작할 때까지 변경 내용이 적용되지 않습니다.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>특정 모듈에 대한 기호 로드 동작을 변경하려면  
  
1.  에 **모듈** 창 모듈을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  가리킨 **자동 기호 로드 설정을** 클릭 하 고 **항상 수동으로 로드** 하거나 **기본**입니다. 디버깅 세션을 다시 시작할 때까지 변경 내용이 적용되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 중단](/previous-versions/visualstudio/visual-studio-2010/7z9se2d8(v=vs.100))   
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [기호 파일(.pdb) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)