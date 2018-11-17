---
title: 중지 시간 | Microsoft Docs
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
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f9b86ea0fa1b7880893e4d7300efbe51a029ce7
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51801799"
---
# <a name="sleep-time"></a>중지 시간
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

타임라인의 이러한 세그먼트는 중지로 분류되는 차단 시간과 관련이 있습니다. 중지 범주는 스레드가 자발적으로 해당 논리 코어를 포기했고 아무 작업도 수행하지 않음을 의미입니다. 이 시간 동안 스레드는 동시성 시각화 도우미가 중지로 간주되는 API에서 차단되었습니다. `Sleep()` 및 `SwitchToThread()` 등의 API는 이 그룹에 속합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)



