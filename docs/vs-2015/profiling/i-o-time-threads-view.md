---
title: I/O 시간(스레드 뷰) | Microsoft Docs
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
- vs.cv.threads.timeline.io
helpviewer_keywords:
- Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab10b52052ddacb005668a2620846f618e45bc62
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51808598"
---
# <a name="io-time-threads-view"></a>I/O 시간(스레드 뷰)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

타임라인의 이러한 세그먼트는 I/O로 분류되는 차단 시간과 관련이 있습니다. 즉, 스레드는 I/O 작업이 끝나기를 대기하고 있습니다. 스레드는 API에서 차단되거나 동시성 시각화 도우미가 I/O로 계산하는 I/O 관련 커널 대기에 의해 차단되었을 수 있습니다. `CreateFile()`, `ReadFile()` 및 `WSARecv()` 등의 API는 이 그룹에 속합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)



