---
title: UI 처리 시간 | Microsoft Docs
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
- vs.cv.threads.timeline.uiprocessing
helpviewer_keywords:
- Concurrency Visualizer, UI Processing Time
ms.assetid: 0ddb05a3-8c6b-448b-8488-2751c1e5abcc
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e35f5f37b0eced2822cb4b019732210bec94495
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555674"
---
# <a name="ui-processing-time"></a>UI 처리 시간
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [UI 처리 시간](https://docs.microsoft.com/visualstudio/profiling/ui-processing-time)합니다.  
  
타임라인의 이러한 세그먼트는 UI 처리로 분류되는 차단 시간과 관련이 있습니다. 이는 스레드가 Windows 메시지를 펌핑 중이거나 다른 UI(사용자 인터페이스) 작업을 수행 중임을 의미합니다. 이 시간 동안 스레드는 동시성 시각화 도우미가 UI 처리로 간주되는 API에서 차단되었습니다. `GetMessage()` 및 `MsgWaitForMultipleObjects()` 등의 API는 이 그룹에 속합니다.  
  
 미리 정의된 차단 API가 식별되지 않은 경우 호출 스택 및 프로필 보고서를 검토하여 지연의 근본 원인을 확인합니다.  
  
 UI 처리 범주는 GUI 응용 프로그램의 응답성을 이해하는 데 중요하며 UI 응답성에 종속된 응용 프로그램에서 유용합니다. 예를 들어 응용 프로그램의 UI 스레드가 UI 처리에서 100% 시간을 달성하는 경우 매우 반응이 빠릅니다. 그러나 UI 스레드가 다른 범주에서 상당한 시간을 소요하는 경우 근본 원인을 찾고 해당 스레드에서 UI가 아닌 범주를 줄이기 위한 옵션을 고려합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)



