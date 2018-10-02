---
title: 네이티브 코드의 스레드 디버깅 팁 | Microsoft Docs
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
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02343da30e4f185a5b4aa236ed9b0b3ef823c4bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543516"
---
# <a name="tips-for-debugging-threads-in-native-code"></a>네이티브 코드의 스레드 디버깅 팁
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [네이티브 코드의 스레드 디버깅 팁](https://docs.microsoft.com/visualstudio/debugger/tips-for-debugging-threads-in-native-code)합니다.  
  
다음은 네이티브 코드에서 스레드를 디버깅할 때 사용할 수 있는 몇 가지 팁입니다.  
  
-   입력 하 여 스레드 정보 블록의 내용을 볼 수 있습니다 `@TIB` 에 **조사식** 창 또는 **간략 한 조사식** 대화 상자.  
  
-   현재 스레드의 마지막 오류 코드를 입력 하 여 볼 수 있습니다 `@Err` 에 **조사식** 창 또는 **간략 한 조사식** 대화 상자.  
  
-   CRT(C Run-Time Libraries) 함수는 다중 스레드 응용 프로그램을 디버깅하는 데 유용합니다. 자세한 내용은 [_malloc_dbg](http://msdn.microsoft.com/library/c97eca51-140b-4461-8bd2-28965b49ecdb)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)



