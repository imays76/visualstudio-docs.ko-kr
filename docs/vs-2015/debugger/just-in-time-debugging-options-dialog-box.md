---
title: Just-in-time, 디버깅, 옵션 대화 상자 | Microsoft Docs
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
- VS.ToolsOptionsPages.Debugger.JIT
- vs.debug.options.JIT
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- Just-In-Time debugging, setting options
- Options dialog box, debugging
ms.assetid: 7f11b2e3-3fb5-449d-b07c-6ecf1d6a487d
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fbe323d5c8939ee5a4088436c906b99b4696254e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49872930"
---
# <a name="just-in-time-debugging-options-dialog-box"></a>옵션 대화 상자, 디버깅, Just-In-Time
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

액세스 하는 **Just In Time** 페이지로 이동 하는 **도구** 메뉴를 클릭 **옵션**합니다. 에 **옵션** 대화 상자에서 **디버깅** 노드와 선택 **Just In Time**합니다. 이 페이지에서는 관리 코드, 네이티브 코드 및 스크립트에 대해 Just-In-Time 디버깅을 사용하도록 설정할 수 있습니다. 자세한 내용은 [Just-In-Time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md)합니다.  
  
 다음과 같은 프로그램 유형에 대해 Just-In-Time 디버깅을 사용하도록 설정할 수 있습니다.  
  
- 관리  
  
- 네이티브  
  
- 스크립트  
  
  Just-In-Time 디버깅은 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 외부에서 시작된 프로그램을 디버깅하는 기술입니다. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 환경 외부에서 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 만든 프로그램을 실행할 수 있습니다. Just-in-time 디버깅을 사용하도록 설정한 상태에서 프로그램이 충돌하면 디버깅할지 여부를 묻는 대화 상자가 표시됩니다.  
  
## <a name="associated-warnings"></a>관련된 경고  
 이 페이지를 방문 하는 경우는 **옵션** 대화 상자에서 다음과 같은 경고 메시지가 표시 될 수 있습니다.  
  
 **다른 디버거가 시간에서 것으로 등록 된 디버거. 복구 하려면 Just In Time 디버깅 또는 Visual Studio 복구를 실행을 사용 하도록 설정 합니다.**  
  
 이 메시지는 다른 디버거(예: 이전 버전의 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 디버거)가 Just-In-Time 디버거로 설정되어 있는 경우에 발생합니다.  
  
 다음과 같은 다른 메시지가 표시될 수도 있습니다.  
  
 **Just-in-time 디버깅 등록 오류가 발견 되었습니다. 복구 하려면 Just In Time 디버깅 또는 Visual Studio 복구를 실행을 사용 하도록 설정 합니다.**  
  
 표시 되 면 이러한 경고가 Just In Time 사용 하 여 디버깅 [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] 문제를 해결할 때까지 관리자 권한이 필요 합니다. 이러한 상황에서 관리자 이외의 권한으로 Just-In-Time 디버깅을 사용하도록 설정하려고 하면 다음과 같은 오류 메시지가 표시됩니다.  
  
 **액세스가 거부 되었습니다. 관리자 Just In Time 디버깅 사용, 했거나 Visual Studio 설치를 복구 합니다.**  
  
## <a name="see-also"></a>참고 항목  
 [옵션 대화 상자, 디버깅](../debugger/debugging-options-dialog-box.md)   
 [방법: 디버거 설정 지정](../debugger/how-to-specify-debugger-settings.md)



