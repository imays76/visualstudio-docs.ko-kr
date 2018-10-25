---
title: '방법: 플래그를 지정 및 스레드의 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09d26c87867e071b7dafce80d95e4bc46cb88bb8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49891377"
---
# <a name="how-to-flag-and-unflag-threads"></a>방법: 스레드에 플래그 지정 및 스레드의 플래그 해제
아이콘 표시 하 여 특별 한 주의가 하려는 스레드에 플래그를 수는 **스레드**를 **병렬 스택** (스레드 뷰) **병렬 조사식**, 및  **GPU 스레드** windows. 이 아이콘은 플래그 설정된 스레드를 다른 스레드와 구분하는 데 도움이 됩니다.  
  
플래그가 지정 된 스레드 권한도에서 별도로 처리 합니다 **스레드** 목록에서 **디버그 위치** 도구 모음 및 다른 다중 스레드 디버깅 창에서. 모든 스레드 또는에서 플래그가 지정 된 스레드만 표시할 수 있습니다 합니다 **스레드** 목록 또는 다른 창에서.
  
### <a name="to-flag-or-unflag-a-thread"></a>스레드에 플래그를 지정하거나 해제하려면 
  
- 에 **스레드** 하거나 **병렬 조사식** 창에서 원하는 스레드를 찾아 선택 하 고 플래그를 지우려면 플래그 아이콘을 클릭 합니다. 
- 에 **병렬 스택** 창에서 스레드 또는 스레드 선택한 그룹을 마우스 오른쪽 단추로 클릭 **플래그 / <thread>**  하거나 **플래그 해제 / <thread>** 합니다.
  
### <a name="to-unflag-all-threads"></a>모든 스레드의 플래그를 해제하려면  
  
-   에 **스레드** 창에서 스레드를 마우스 오른쪽 단추로 클릭 하 고 클릭 **모든 스레드 플래그 해제**합니다.
-   에 **병렬 조사식** 창에서 모든 플래그가 지정 된 스레드만, 그런 다음 마우스 오른쪽 단추로 클릭 하 고 선택 **플래그 해제**합니다.  
  
### <a name="to-display-only-flagged-threads"></a>플래그가 지정된 스레드만 표시하려면  
  
-   선택 된 **스레드 스레드만 표시** 다중 스레드 디버깅 창 중 하나에 단추입니다.  
  
### <a name="to-flag-just-my-code"></a>내 코드만 플래그를 설정하려면  
  
1.  맨 위에 있는 도구 모음에는 **스레드** 창 플래그 아이콘을 클릭 합니다.  
  
2.  드롭다운 목록에서 클릭 **내 코드만 플래그**합니다.  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>선택한 모듈과 연결된 스레드에 플래그를 설정하려면  
  
1.  도구 모음에서의 **스레드** 창에서 플래그 아이콘을 클릭 합니다.  
  
2.  드롭다운 목록에서 클릭 **사용자 지정 모듈 선택 영역 플래그**합니다.  
  
3.  에 **모듈 선택** 대화 상자에서 원하는 모듈을 선택 합니다.  
  
4.  (선택 사항) 에 **검색** 특정 모듈에 대 한 검색할 문자열을 입력 합니다.  
  
5.  **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [다중 스레드 응용 프로그램 디버깅 시작](../debugger/get-started-debugging-multithreaded-apps.md)  
 [연습: 스레드 창 사용 하는 다중 스레드 응용 프로그램 디버그](../debugger/how-to-use-the-threads-window.md)