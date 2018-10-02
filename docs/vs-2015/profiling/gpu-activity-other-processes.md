---
title: GPU 작업(다른 프로세스) | Microsoft 문서
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
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94076c392223fb38d98c1c20b68cf76507955715
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556116"
---
# <a name="gpu-activity-other-processes"></a>GPU 작업(다른 프로세스)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [GPU 작업 (다른 프로세스)](https://docs.microsoft.com/visualstudio/profiling/gpu-activity-other-processes)합니다.  
  
동시성 시각화 도우미의 스레드 뷰에 있는 **GPU 작업(다른 프로세스)** 세그먼트는 시스템의 다른 프로세스를 대신해서 GPU가 요청을 처리 중인 시간을 나타냅니다. 이러한 요청은 DMA(직접 메모리 액세스) 패킷으로 GPU에 전송됩니다.  세그먼트 길이는 GPU에서 패킷이 처리된 시간을 나타냅니다.  
  
 이 종류의 세그먼트를 선택하면 **현재** 탭의 보고서에 처리된 패킷에 대한 정보가 표시됩니다.  이 정보에는 DirectX 엔진과 연관된 하드웨어 큐에서 패킷이 대기하는 데 걸린 시간, 패킷을 전송한 프로세스, 패킷을 처리하는 데 필요한 시간이 포함됩니다.



