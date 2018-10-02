---
title: 'CA1600: 유휴 상태 프로세스 우선 순위를 사용 하지 마십시오 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b211c1ab646d27cf32290d3c5c306719ba7decff
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47592082"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: 유휴 상태 프로세스 우선 순위를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1600: 유휴 상태 프로세스 우선 순위를 사용 하지 않는](https://docs.microsoft.com/visualstudio/code-quality/ca1600-do-not-use-idle-process-priority)합니다.

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|범주|Microsoft.Mobility|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 이 규칙은 프로세스 설정 된 경우 `ProcessPriorityClass.Idle`합니다.

## <a name="rule-description"></a>규칙 설명
 프로세스 우선 순위를 유휴 상태로 설정하지 마십시오. 프로세스를 `System.Diagnostics.ProcessPriorityClass.Idle` 유휴, 고 블록이 대기 하는 경우에 CPU를 차지 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 프로세스로 `ProcessPriorityClass.BelowNormal`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 유휴 프로세스 우선 순위 필수 항목이 며 이동성 고려 사항을 안전 하 게 무시할 수 있습니다 하는 경우에이 규칙을 표시 하지 않습니다.



