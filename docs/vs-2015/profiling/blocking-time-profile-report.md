---
title: 차단 시간 프로필 보고서 | Microsoft 문서
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
- vs.cv.threads.report.blocking
helpviewer_keywords:
- Concurrency Visualizer, Blocking Time Profile Report
ms.assetid: 3bc45af0-3ba6-4fa3-a336-be8e9ae95107
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae0c4f34f0d3447f63afbf08e9d788304b2d353f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541948"
---
# <a name="blocking-time-profile-report"></a>차단 시간 프로필 보고서
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [차단 시간 프로필 보고서](https://docs.microsoft.com/visualstudio/profiling/blocking-time-profile-report)합니다.  
  
프로필 보고서에서는 "I/O" 또는 "동기화" 등의 각 차단 범주와 관련된 호출 스택에 대한 집계 차단 시간 데이터를 제공합니다. 선점 보고서에는 선점 인스턴스 수와 함께 현재 프로세스를 선점한 프로세스가 나열됩니다. 차단 프로필 보고서를 빌드하기 위해 이 도구는 차단 API 호출을 수집하고 이를 호출 스택 트리에 누적합니다. 이 보고서에 표시되는 데이터는 현재 시간 범위, 숨겨진 스레드 및 적용할 수 있는 다음 두 개의 필터에 따라 달라집니다.  
  
-   [내 코드만]을 선택하면 사용자 코드와 사용자 코드 아래에 한 수준이 포함된 스택 프레임만 표시됩니다.  
  
-   노이즈 감소 값을 설정하면 지정된 빈도보다 낮은, 데이터 정렬된 스택을 건너뜁니다.  
  
 호출 트리 항목을 확장해서 차단 시간이 사용된 코드 줄을 찾습니다. 항목에 대한 소스 줄을 찾으려면 해당 바로 가기 메뉴에서 **소스 보기**를 선택합니다. 이 항목을 호출한 코드 줄을 찾으려면 바로 가기 메뉴에서 **호출 사이트 보기**를 선택합니다. 사용할 수 있는 호출 사이트가 하나뿐인 경우 이 명령을 사용하면 해당 호출 사이트에 대한 강조 표시된 코드 줄에 연결됩니다. 여러 호출 사이트를 사용할 수 있는 경우 이 명령을 사용하면 사용자가 항목을 선택한 후 **소스로 이동** 단추를 선택해서 강조 표시된 호출 사이트를 찾을 수 있는 대화 상자가 열립니다. 인스턴스가 가장 많거나, 시간이 가장 오래 걸리거나, 두 항목이 모두 가장 높은 호출 사이트에 대해서는 소스 코드를 보는 것이 종종 가장 유용한 방법입니다.  
  
## <a name="blocking-time-report-columns"></a>차단 시간 보고서 열  
 다음 표에서는 각 차단 시간 보고서에 대한 열을 보여 줍니다.  
  
|열 이름|설명|  
|-----------------|-----------------|  
|이름|호출 스택의 각 수준에 대한 함수의 이름입니다.|  
|인스턴스|보이는 기간에 대한 차단 호출의 인스턴스 수입니다.|  
|포함 차단 시간|호출 스택 트리의 이 수준까지 이르는 모든 스택에 소요된 총 차단 시간입니다. 포함 수는 이 함수에 대한 제외 차단 시간과 모든 하위 노드에 대한 제외 차단 시간의 합입니다.|  
|제외 차단 시간|이 함수가 호출 스택에서 최하위 수준에 있는 동안 소요된 총 차단 시간입니다. 제외 차단 시간 값이 높은 고유한 호출 스택 항목이 관심 함수일 수 있습니다.|  
|API/대기 범주|호출 스택의 최하위 수준에 있는 함수에만 표시됩니다. 차단 호출의 서명이 인식되는 곳에서는 차단 API의 이름이 제공됩니다. 시그니처가 인식되지 않으면 커널에서 보고된 정보가 제공됩니다.|  
|설명|함수의 정규화된 이름입니다. 여기에는 사용 가능한 경우 줄 수가 포함됩니다.|  
  
### <a name="synchronization"></a>동기화  
 동기화 보고서에는 동기화에서 차단되는 세그먼트를 처리하는 호출 및 각 호출 스택의 집계 차단 시간이 표시됩니다. 자세한 내용은 [동기화 시간](../profiling/synchronization-time.md)을 참조하세요.  
  
### <a name="sleep"></a>Sleep  
 중지 보고서에는 중지에 사용된 시간으로 전환된 차단 시간을 처리하는 호출 및 각 호출 스택의 집계 차단 시간이 표시됩니다. 자세한 내용은 [중지 시간](../profiling/sleep-time.md)을 참조하세요.  
  
### <a name="io"></a>I/O  
 I/O 보고서에는 I/O에서 차단되는 세그먼트를 처리하는 호출 및 각 호출 스택의 집계 차단 시간이 표시됩니다. 자세한 내용은 [I/O 시간(스레드 뷰)](../profiling/i-o-time-threads-view.md)를 참조하세요.  
  
### <a name="memory-management"></a>메모리 관리  
 메모리 관리 보고서에는 메모리 관리 작업에서 차단되는 세그먼트를 처리하는 호출 및 각 호출 스택의 집계 차단 시간이 표시됩니다. 자세한 내용은 [메모리 관리 시간](../profiling/memory-management-time.md)을 참조하세요.  
  
### <a name="preemption"></a>선점  
 선점 보고서에는 인스턴스 수와 함께 현재 프로세스를 선점한 프로세스가 나열됩니다.  각 프로세스를 확장해서 현재 프로세스에서 스레드를 교체한 특정 스레드를 보고 스레드당 선점 인스턴스 분석을 볼 수 있습니다. 선점은 일반적으로 코드의 문제보다는 운영 체제에 의해 프로세스에 적용되기 때문에 이 차단 보고서는 다른 보고서보다 실용성이 낮습니다. 자세한 내용은 [선점 시간](../profiling/preemption-time.md)을 참조하세요.  
  
### <a name="ui-processing"></a>UI 처리  
 UI 처리 보고서에는 UI 처리 블록에서 차단되는 차단 세그먼트를 처리하는 호출 및 각 호출 스택의 집계 차단 시간이 표시됩니다. 자세한 내용은 [UI 처리 시간](../profiling/ui-processing-time.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)


