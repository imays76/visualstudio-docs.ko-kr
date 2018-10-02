---
title: 옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 38374893aea62af1b664065edf0ca9195f3dd301
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564986"
---
# <a name="options-dialog-box--projects-and-solutions-build-and-run"></a>옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)합니다.  
  
  
이 대화 상자에서 동시에 빌드할 수 있는 Visual C++ 또는 Visual C# 프로젝트의 최대 개수, 특정 기본 빌드 동작 및 일부 빌드 로그 설정을 지정할 수 있습니다. 열려는 합니다 **옵션** 대화 상자에서 **도구**를 **옵션** 메뉴 모음에서. 이 옵션 집합에 액세스 하려면 확장 **프로젝트 및 솔루션**를 선택한 후 **빌드 및 실행**합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **최대 병렬 프로젝트 빌드 수**  
 동시에 빌드할 수 있는 Visual C++ 및 Visual C# 프로젝트의 최대 개수를 지정합니다. 빌드 프로세스를 최적화하기 위해 최대 병렬 프로젝트 빌드 수는 자동으로 컴퓨터의 CPU 수로 설정됩니다. 최대값은 32입니다.  
  
 **실행할 때 시작 프로젝트와 종속성만 빌드**  
 F5 키를 선택 하면이 확인란을 선택한 경우에 작성 된 시작 프로젝트만 및 해당 종속성 선택 **디버그**를 **시작** 메뉴 모음 또는 선택 **빌드**를 **빌드** 메뉴 모음에서. F5 키를 선택 하면이 확인란의 선택을 취소 하는 경우 작성 된 모든 프로젝트, 종속성 및 솔루션 파일 선택 **디버그**를 **시작** 메뉴 모음 또는 선택 **빌드**를 **빌드** 메뉴 모음에서. 기본적으로 이 옵션은 선택 취소되어 있습니다.  
  
 **실행 시 프로젝트가 만료된 경우**  
 > [!NOTE]
>  이 목록은 [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] 프로젝트에만 적용됩니다.  
  
 기본적으로 메시지가 표시 됩니다 F5 키를 선택 하거나 선택 하면 오래 된 프로젝트 구성 **디버그**하십시오 **시작** 메뉴 모음에서. 프로젝트를 빌드할지 여부 및 메시지를 표시할지 여부를 지정할 수 있습니다. 이 옵션을 사용하여 메시지의 표시 여부 및 메시지를 표시하지 않는 경우의 빌드 동작을 지정합니다.  
  
 **항상 빌드**  
 메시지 상자가 표시되지 않고 구성이 오래된 경우에도 프로젝트가 빌드됩니다. 이 옵션을 선택 하면 설정 합니다 **이 대화 상자를 다시 표시 안 함** 메시지 상자를 선택한는 **예** 단추.  
  
 **빌드 안 함**  
 메시지 상자가 표시되지 않고 프로젝트가 빌드되지 않습니다. 선택 하면이 옵션이 설정 되어는 **이 대화 상자를 다시 표시 안 함** 메시지 상자를 선택한 합니다 **No** 단추.  
  
 **빌드 여부 묻기**  
 프로젝트 구성이 오래될 때마다 메시지 상자를 표시합니다.  
  
 **실행 시 빌드 또는 배포 오류가 발생한 경우**  
 빌드를 시작할 때 빌드 오류가 발생 하는 경우는 **빌드** 메뉴에서 메시지가 표시 됩니다. 응용 프로그램을 시작하여 계속할지 여부 및 빌드 오류가 발생할 때마다 메시지를 표시할지 여부를 지정할 수 있습니다. 이 옵션을 사용하여 메시지의 표시 여부 및 메시지를 표시하지 않는 경우의 동작을 지정합니다.  
  
> [!NOTE]
>  이 옵션은 [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] 프로젝트에만 적용됩니다.  
  
 **시작 여부 묻기**  
 빌드 오류가 발생할 때마다 메시지 상자를 표시합니다.  
  
 **시작 하지 않음**  
 메시지 상자가 표시되지 않고 응용 프로그램이 시작되지 않습니다. 선택 하면이 옵션이 설정 되어는 **이 대화 상자를 다시 표시 안 함** 메시지 상자에서 확인 한 다음는 **No** 단추.  
  
 **이전 버전 시작**  
 메시지 상자가 표시되지 않고 응용 프로그램의 새로 빌드된 버전이 시작되지 않습니다. 이 옵션을 선택 하면 설정 합니다 **이 대화 상자를 다시 표시 안 함** 메시지 상자에서 확인란을 선택한 후를 **예** 단추.  
  
 **새 솔루션에 대해 현재 선택한 프로젝트를 시작 프로젝트로 사용**  
 이 확인란이 선택된 경우 새 솔루션이 현재 선택한 프로젝트를 시작 프로젝트로 사용합니다.  
  
 **MSBuild 프로젝트 빌드 출력의 자세한 정도**  
 빌드에 대한 **출력** 창에 표시되는 정보의 양을 결정합니다.  
  
 **MSBuild 프로젝트 빌드 로그 파일의 자세한 정도**  
 > [!NOTE]
>  이 옵션은 Visual C++ 프로젝트에만 적용됩니다.  
  
 \\...\\*ProjectName*\Debug\\*ProjectName*.log에 있는 빌드 로그 파일에 작성되는 정보의 양을 결정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일 및 빌드](../../ide/compiling-and-building-in-visual-studio.md)



