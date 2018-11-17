---
title: 'DA0004: 프로세서 사용률이 높습니다. | Microsoft Docs'
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
- vs.performance.rules.DAHighProcessorUsage
- vs.performance.rules.DA0004
- vs.performance.DA0004
- vs.performance.4
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a942a26bb4cd8ccca94fd442250fe8a239cba4ed
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51764037"
---
# <a name="da0004-high-processor-usage"></a>DA0004: 프로세서 사용률이 높습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

규칙 Id | DA0004 |  
| 범주 | 프로 파일링 도구 사용 |  
| 프로 파일링 방법 | 계측 샘플링 |  
| 메시지 | 프로세서 사용률이 75% 이상 일관 되 게 됩니다. CPU 바인딩된 응용 프로그램에 대 한 샘플링 모드를 사용 하는 것이 좋습니다. |  
| 규칙 유형 | 정보 |  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링할 경우 이 규칙을 트리거하려면 10개 이상의 샘플을 수집해야 합니다.  
  
## <a name="cause"></a>원인  
 계측 방법을 사용하여 수집된 프로파일링 데이터에서 프로세서(CPU) 사용률이 상당히 높았습니다. CPU 바인딩된 응용 프로그램을 프로파일링할 경우 샘플링 프로파일링 방법을 사용해 보세요.  
  
## <a name="rule-description"></a>규칙 설명  
 이 프로파일링을 실행하는 동안 하나 이상의 프로세서가 지속적으로 사용 중이었습니다. 높은 CPU 사용률은 CPU 바인딩된 응용 프로그램을 나타낼 수 있습니다. 계측된 프로필은 대개 CPU 사용 시나리오를 조사하는 가장 효과적인 방법이 아닙니다. 프로세서에서 명령을 실행하는 데 시간이 오래 걸리는 응용 프로그램을 프로파일링할 경우 대개 샘플링이 더 효과적입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 함수 타이밍이 필요하거나 프로세서 병목 현상보다는 입/출력 이해에 더 관심이 있는 경우가 아니면 계측 방법 대신 샘플링 방법을 사용해서 응용 프로그램을 다시 프로파일링해 보세요.




