---
title: GPU 작업 그래프 | Microsoft 문서
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
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5a0ef828b221219c3abae0e46ec40d21b6b045c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556109"
---
# <a name="gpu-activity-graph"></a>GPU 작업 그래프
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [GPU 작업 그래프](https://docs.microsoft.com/visualstudio/profiling/gpu-activity-graph)합니다.  
  
동시성 시각화 도우미에서 GPU 작업 그래프는 시간 경과에 따라 사용 중인 DirectX 엔진의 개수로 측정되는 시스템의 DirectX 작업 수준을 표시합니다.  그래프에는 사용된 특정 엔진이 표시되지 않습니다.  엔진은 GPU 작업을 처리 중일 때 사용 중인 것으로 간주됩니다.  
  
## <a name="gpu-activity-graph-colors"></a>GPU 작업 그래프 색상  
 녹색은 현재 프로세스에서 DirectX 엔진이 사용되었음을 나타냅니다.  
  
 밝은 회색은 시스템에서 다른 프로세스가 DirectX 엔진을 사용되었음을 나타냅니다. 다른 프로세스의 DirectX 엔진 사용을 줄이려면 시스템에서 실행되는 다른 프로세스 수를 줄입니다.  
  
 흰색은 시스템에서 사용하지 않는 DirectX 엔진의 가용성을 나타냅니다. 이러한 엔진은 이를 활용할 수 있는 더 많은 기회를 발견할 경우 프로세스에 사용할 수 있습니다. 일부 엔진은 특정 종류의 작업에만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용률 뷰](../profiling/utilization-view.md)


