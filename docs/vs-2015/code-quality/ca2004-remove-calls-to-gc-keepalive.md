---
title: 'CA2004: GC에 대 한 호출을 제거 합니다. KeepAlive | Microsoft Docs'
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
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8fbaa0bae44b09cef1d75c31c342ac6cf3e463df
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591131"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: GC.KeepAlive에 대한 호출을 제거하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2004: GC에 대 한 호출을 제거 합니다. KeepAlive](https://docs.microsoft.com/visualstudio/code-quality/ca2004-remove-calls-to-gc-keepalive)합니다.

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|범주|Microsoft.Reliability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 클래스를 사용 하 여 `SafeHandle` 여전히에 대 한 호출을 포함 하지만 `GC.KeepAlive`합니다.

## <a name="rule-description"></a>규칙 설명
 변환 하는 경우 `SafeHandle` 사용에 대 한 모든 호출을 제거 `GC.KeepAlive` (개체). 이 경우 클래스 해야 호출할 필요가 없습니다 `GC.KeepAlive`, 종료 자가 없는 있지만 의존 가정 `SafeHandle` 에 OS 핸들을 완료 합니다.  하지만 비용에 대 한 호출을 두면 `GC.KeepAlive` 인식 성능을 기준으로 무시할 수 없습니다는에 대 한 호출 `GC.KeepAlive` 필요 하거나 더 이상 존재 하는 문제는 코드를 하기 어렵게 만듭니다 수명을 해결 하는 데 충분 유지 관리 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 에 대 한 호출을 제거 `GC.KeepAlive`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 변환할 기술적으로 올바르지 않은 경우에이 경고를 표시 하지 않을 수 `SafeHandle` 클래스에서 사용 합니다.



