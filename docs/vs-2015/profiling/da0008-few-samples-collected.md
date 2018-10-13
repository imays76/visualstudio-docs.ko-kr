---
title: 'DA0008: 수집되는 샘플 수가 적습니다. | Microsoft 문서'
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
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6e294c03f958259f26938865a3e26c6fb7669d6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49289811"
---
# <a name="da0008-few-samples-collected"></a>DA0008: 수집되는 샘플 수가 적습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

규칙 Id | DA0008 |  
| 범주 | 프로 파일링 도구 사용 |  
| 프로 파일링 방법을 | 샘플링 |  
| 메시지 | 샘플이 몇 개만 수집 되었습니다. 보다 의미 있는 결과 대 한 실행 또는 더 빠른 샘플링 주기를 더는 것이 좋습니다. |  
| 규칙 유형 | 정보 |  
  
## <a name="cause"></a>원인  
 프로파일링 실행에서 샘플이 몇 개만 수집되었습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 샘플링 방법을 사용할 경우 데이터가 실제 프로그램 동작을 나타내는지 확인하려면 통계적으로 의미 있는 수의 샘플을 수집해야 합니다. 샘플링 오류를 최소화하려면 프로그램 명령 실행 동작의 샘플을 1000개 이상 수집해야 합니다. 충분한 샘플을 수집하지 않으면 프로파일링 데이터를 분석할 때 결과가 잘못될 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 통계적으로 의미 있는 결과를 얻으려면 더 오래 실행되는 응용 프로그램을 프로파일링하거나 더 빠른 샘플링 주기를 사용해 보세요. Visual Studio IDE에서 샘플링 주기를 변경하는 방법에 대한 자세한 내용은 [방법: 샘플링 이벤트 선택](../profiling/how-to-choose-sampling-events.md)을 참조하세요. 프로파일링 도구 명령줄을 사용할 때 샘플링 주기를 변경하는 방법에 대한 자세한 내용은 [VSPerfCmd](../profiling/vsperfcmd.md) 참조에서 [Timer](../profiling/timer.md)를 참조하세요.



