---
title: '방법: ActiveX 컨트롤 디버그 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.controls.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- testing [Visual Studio], test containers
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- data-bound controls, ActiveX
- test container
- containers, specifying for debug sessions
- ActiveX controls, debugging
- testing [Visual Studio], ActiveX controls
ms.assetid: bbc02cf7-a7e6-44fe-99af-87a43e1d7251
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cc47ba913ba9da1ecfe8e0df34894c31545e1734
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551189"
---
# <a name="how-to-debug-an-activex-control"></a>방법: ActiveX 컨트롤 디버깅
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: ActiveX 컨트롤 디버그](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-an-activex-control)합니다.  
  
참고]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
 ActiveX 컨트롤을 디버깅하려면 컨트롤을 실행할 컨테이너(실행 파일)를 지정해야 합니다.  
  
### <a name="to-specify-a-container-for-the-debug-session"></a>디버그 세션에 사용할 컨테이너를 지정하려면  
  
1.  솔루션 탐색기에서 프로젝트를 선택합니다.  
  
2.  **뷰** 메뉴 선택 **속성 페이지**합니다.  
  
3.  에 **프로젝트 속성 페이지** 대화 상자를 열고 합니다 **구성 속성** 폴더를 선택한 **디버깅**.  
  
4.  아래는 **디버깅** 범주를 찾습니다는 **명령** 속성입니다.  
  
5.  컨테이너의 경로 이름을 지정하십시오. 예를 들어, C:\Program Files\Internet Explorer\IEXPLORE.EXE와 같이 입력하십시오.  
  
6.  컨테이너로 Internet Explorer를 지정 하 고 Active Desktop을 사용 하는 경우 입력 `/new` 에 **명령 인수** 상자입니다.  
  
7.  **확인**을 클릭합니다.  
  
     컨테이너를 지정 하지 않는 경우는 **프로젝트 속성 페이지** 대화 상자, 디버깅을 시작할 때 컨테이너를 지정할 수 있습니다. 디버깅을 시작 하는 실행 명령을 선택 하면 합니다 [디버깅 세션 대화 상자에 대 한 실행 파일](../debugger/executable-for-debugging-session-dialog-box.md) 나타납니다. 대화 상자에서 컨테이너의 경로 이름을 지정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ActiveX 컨트롤](http://msdn.microsoft.com/library/52aaec4d-3889-402e-b57d-758078f8ac57)   
 [속성 및 이벤트 테스트 컨테이너를 사용 하 여 테스트](http://msdn.microsoft.com/library/626867cf-fe53-4c30-8973-55bb93ef3917)   
 [COM 및 ActiveX 디버깅](../debugger/com-and-activex-debugging.md)   
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)



