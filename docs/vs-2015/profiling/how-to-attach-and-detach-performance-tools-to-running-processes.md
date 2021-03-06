---
title: '방법: 실행 중인 프로세스에 성능 도구 연결 및 분리 | Microsoft 문서'
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
- vs.performance.attach
helpviewer_keywords:
- performance tools, attach process
- profiling tools, detach process
- profiling tools, attach process
- performance tools, detach process
- profiler
ms.assetid: 56a99c39-e7f6-4f48-ae56-04ab8e022bf7
caps.latest.revision: 35
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 931608decb44f0e49cb4ae2984b9cbf724a63d56
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51778243"
---
# <a name="how-to-attach-and-detach-performance-tools-to-running-processes"></a>방법: 실행 중인 프로세스에 성능 도구 연결 및 분리
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

프로파일러를 사용하여 실행 프로세스에 연결하거나 실행 프로세스에서 분리하여 더 쉽게 성능 데이터를 샘플링하고 수집할 수 있습니다. 이 방법을 사용하면 응용 프로그램 로드 시간에 대한 데이터를 수집하지 않거나 특정 상태에 도달한 후 프로세스의 성능을 모니터링하려고 할 때 프로세스를 프로파일링할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] IDE(통합 개발 환경) 내에서 수행되는 프로세스 연결 및 분리에는 다음 단계가 적용됩니다. 명령줄 도구를 사용하는 방법에 대한 자세한 내용은 [명령줄에서 프로파일링](../profiling/using-the-profiling-tools-from-the-command-line.md)을 참조하세요. 서비스를 프로파일링하는 방법에 대한 자세한 내용은 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)을 참조하세요.  
  
 프로파일링할 수 있는 프로세스는 컴퓨터의 관리자가 설정한 사용자 액세스 권한에 따라 결정됩니다. 예를 들어 사용자 계정에 다음에 대한 사용 권한이 있을 수 있습니다.  
  
- 관리자가 드라이버 및 서비스를 시작하도록 설정한 경우 고급 프로파일링 기능.  
  
- 샘플 프로파일링만(도메인 사용자).  
  
- 모든 사용자에게 프로파일링 액세스 거부.  
  
  자세한 내용은 [프로파일링 및 Windows Vista 보안](../profiling/profiling-and-windows-vista-security.md) 및 [VSPerfCmd](../profiling/vsperfcmd.md)의 ADMIN 옵션을 참조하세요.  
  
### <a name="to-attach-to-a-running-process"></a>실행 중인 프로세스에 연결하려면  
  
1.  **분석** 메뉴에서 **프로파일러**를 가리키고 **연결/분리**를 클릭합니다.  
  
     \- 또는 -  
  
     **성능 탐색기**에서 성능 세션을 마우스 오른쪽 단추로 클릭한 다음 **연결/분리**를 클릭합니다.  
  
     **프로세스에 프로파일러 연결** 대화 상자가 나타납니다.  
  
2.  연결할 프로세스의 이름을 클릭합니다.  
  
3.  **연결**을 클릭합니다.  
  
### <a name="to-detach-from-a-running-process"></a>실행 중인 프로세스에서 분리하려면  
  
1.  **분석** 메뉴에서 **프로파일러**를 가리키고 **연결/분리**를 클릭합니다.  
  
     \- 또는 -  
  
     **성능 탐색기**에서 성능 세션을 마우스 오른쪽 단추로 클릭한 다음 **연결/분리**를 클릭합니다.  
  
     **프로세스에 프로파일러 연결** 대화 상자가 나타납니다.  
  
2.  분리할 이미지의 이름을 클릭합니다.  
  
3.  **분리**를 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 수집 제어](../profiling/controlling-data-collection.md)   
 [성능 세션 개요](../profiling/performance-session-overview.md)   
 [방법: 성능 데이터 수집 시작 및 종료](../profiling/how-to-start-and-end-performance-data-collection.md)   
 [프로파일링 및 Windows Vista 보안](../profiling/profiling-and-windows-vista-security.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)



