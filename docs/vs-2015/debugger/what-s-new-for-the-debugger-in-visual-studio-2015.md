---
title: Visual Studio 2015 디버거의 새로운 기능 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
caps.latest.revision: 86
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b7a854e872a7739054379b1f6d01794f142f448
ms.sourcegitcommit: aea5cdb76fbc7eb31d1e5cc3c8d6adb0c743220f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "47593123"
---
# <a name="whats-new-for-the-debugger-in-visual-studio-2015"></a>Visual Studio 2015 디버거의 새로운 기능
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [디버거에 대 한 새로운](https://docs.microsoft.com/visualstudio/debugger/what-s-new-for-the-debugger-in-visual-studio)합니다.  
  
Visual Studio 2015 업데이트 1 디버깅 및 진단의 모든 새로운 기능에 대한 자세한 내용은 [Visual Studio 2015 업데이트 1 릴리스 정보](https://www.visualstudio.com/news/vs2015-update1-vs#debug)를 참조하세요.  
  
 Visual Studio 2015 RTM 디버깅 및 진단의 모든 새로운 기능에 대한 자세한 내용은 [Visual Studio 2015 릴리스 정보](https://www.visualstudio.com/news/vs2015-vs#debug)를 참조하세요.  
  
## <a name="visual-studio-2015-update-1-changes"></a>Visual Studio 2015 업데이트 1 변경 내용  
 C++ 편집하며 계속하기는 더 많은 기능을 지원합니다. 자세한 내용은 [편집 하며 계속 하기 (Visual c + +)](../debugger/edit-and-continue-visual-cpp.md)합니다.  
  
 Visual C++ 액세스 위반을 디버깅하기 위해 새 예외 대화 상자에서 해당 예외를 발생시킨 포인터를 지정합니다. 자세한 내용은 참조 하십시오 [액세스 위반을 어떻게 디버그할 수 있습니다?](../debugger/how-can-i-debug-an-access-violation-q.md) 고 [Visual Studio 2015 업데이트 1에서 c + + 액세스 위반 디버깅 향상](http://blogs.msdn.com/b/visualstudioalm/archive/2015/10/29/improvement-to-debugging-c-access-violations-in-visual-studio-2015-update-1.aspx)  
  
## <a name="visual-studio-2015-rtm-debugger-ui-and-hotkey-changes"></a>Visual Studio 2015 RTM 디버거 UI 및 바로 가기 키 변경  
 예외 및 중단점 UI에 중요한 UI 변경 사항이 있습니다.  
  
### <a name="breakpoints"></a>중단점  
 Visual Studio 2015에는 중단점을 구성하는 새로운 방법, 즉 **중단점 설정** 창이 있습니다.  
  
 다음은 기본적인 중단점 창 및 바로 가기 키를 요약한 내용입니다.  
  
|기능|메뉴 위치|바로 가기 키|  
|-------------|-------------------|------------|  
|새 중단점, 중단점 설정/해제|**디버그/중단점 설정/해제**<br /><br /> 편집기에서 상황에 맞는 메뉴 / **중단점 삽입**<br /><br /> 왼쪽 여백 클릭|F9|  
|새 함수 중단점|**디버그 / 새 중단점 / 함수 중단점**|Visual Studio 2015 RTM (업데이트 없음)를 사용 하 여 ALT + F9, B<br /><br /> Visual Studio 2015 업데이트 1 이상 버전을 사용 하 여 CTRL + B|  
|**중단점** 창|**디버그 / Windows / 중단점**|Ctrl+Alt+B|  
|**중단점 설정**, **조건**|중단점에서 상황에 맞는 메뉴 / **조건**|Alt + F9, C 키|  
|**중단점 설정**, **작업**|중단점에서 상황에 맞는 메뉴 / **작업**|바로 가기 키 없음|  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
1.  [중단점 사용](../debugger/using-breakpoints.md)  
  
2.  [새로운 중단점 구성 환경](http://blogs.msdn.com/b/visualstudioalm/archive/2014/10/06/new-breakpoint-configuration-experience.aspx)  
  
3.  [중단점 구성 환경](http://channel9.msdn.com/Events/Visual-Studio/Connect-event-2014/711)  
  
### <a name="exception-settings"></a>예외 설정  
 새로운 **예외 설정** 창에서는 단일 예외 또는 예외 범주에 적용할 예외 처리의 종류를 지정할 수 있습니다.  
  
|기능|메뉴 위치|Hotkey|  
|-------------|-------------------|------------|  
|**예외 설정** 창|**디버그 / Windows / 예외 설정**|Ctrl+Alt+E|  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
1.  [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)  
  
2.  [새 예외 창](http://blogs.msdn.com/b/visualstudioalm/archive/2015/02/23/the-new-exception-settings-window-in-visual-studio-2015.aspx)  
  
### <a name="edit-and-continue"></a>편집하며 계속하기  
 Visual Studio 2015에서는 **도구 / 옵션 / 디버깅 / 일반** 페이지에서 편집하며 계속하기를 설정할 수 있습니다. 이전 버전에서는 이러한 설정이 별도의 옵션 범주에 있었습니다.  
  
### <a name="attach-to-process"></a>프로세스에 연결  
 Visual Studio 2015 프로세스에 연결 명령을 디버그 메뉴에서만 사용할 수 있습니다. 이전 버전에서는 도구 메뉴에서도 사용할 수 있었습니다. Ctrl+Alt+P 바로 가기 키는 모든 버전에서 작동합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)



