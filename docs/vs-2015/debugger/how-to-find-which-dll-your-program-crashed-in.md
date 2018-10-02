---
title: '방법: 프로그램에서 충돌이 발생 하는 DLL 찾기 | Microsoft Docs'
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
- vs.debug.dll
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8dc06d433739b4c0706374a691474207a45c5766
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551064"
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>방법: 프로그램에서 충돌이 발생하는 DLL 찾기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 찾기는 DLL Your 프로그램 충돌에서](https://docs.microsoft.com/visualstudio/debugger/how-to-find-which-dll-your-program-crashed-in)합니다.  
  
참고]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
 시스템 DLL 또는 다른 사람의 코드를 호출하는 동안 응용 프로그램에 충돌이 발생하면 충돌 발생 시 활성 상태였던 DLL을 찾아야 합니다. 사용자 프로그램 외부 DLL 충돌을 발생 하는 경우 사용 하 여 위치를 식별할 수 있습니다 합니다 **모듈** 창입니다.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>모듈 창을 사용하여 충돌이 발생한 위치를 찾으려면  
  
1.  충돌이 발생한 주소를 기록합니다.  
  
2.  에 **디버그** 메뉴 선택 **Windows**를 클릭 하 고 **모듈**합니다.  
  
3.  에 **모듈** 창 찾기 합니다 **주소** 열입니다. 이 열을 표시하려면 스크롤 막대를 사용해야 할 수도 있습니다.  
  
4.  클릭 합니다 **주소** 주소별로 Dll을 정렬 하려면 열 맨 위에 있는 단추입니다.  
  
5.  정렬된 목록을 조사하여 충돌 위치가 속하는 주소 범위를 가진 DLL을 찾습니다.  
  
6.  확인 합니다 **이름** 및 **경로** DLL 이름 및 경로 참조 하는 열.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 네이티브 Dll 디버그](../debugger/how-to-debug-native-dlls.md)   
 [방법: 모듈 창 사용](../debugger/how-to-use-the-modules-window.md)





