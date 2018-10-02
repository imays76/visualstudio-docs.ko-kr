---
title: ': 인덱서 ca1023 다차원 | Microsoft Docs'
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
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e1b1022484db26e6ff8fbc0046333f187753bb53
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591112"
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: 다차원 인덱서는 사용하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1023: 다차원 인덱서 설정 되지 않습니다](https://docs.microsoft.com/visualstudio/code-quality/ca1023-indexers-should-not-be-multidimensional)합니다.

|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 Public 또는 protected 형식이 둘 이상의 인덱스를 사용 하는 public 또는 protected 인덱서를 포함 합니다.

## <a name="rule-description"></a>규칙 설명
 인덱서, 즉 인덱싱된 속성에는 단일 인덱스를 사용 해야 합니다. 다차원 인덱서는 라이브러리의 유용성을 크게 줄일 수 있습니다. 디자인 여러 인덱스에 필요한 경우 형식 논리 데이터 저장소를 나타내는지 여부를 다시 고려해 보아야 합니다. 그러지 않으면 메서드를 사용 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 유일한 정수나 문자열 인덱스를 사용 하도록 디자인을 변경 하거나 인덱서 대신 메서드를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 비표준 인덱서에 대 한 필요성을 신중 하 게 고려한 후에이 규칙에서 경고를 표시 합니다.

## <a name="example"></a>예제
 다음 예제에서는 형식 `DayOfWeek03`, 규칙을 위반 하는 다차원 인덱서를 사용 하 여 합니다. 인덱스 변환의 형식으로 볼 수 있습니다 및 메서드로 노출 보다 적절 하 게 됩니다. 형식으로 다시 디자인 `RedesignedDayOfWeek03` 규칙을 충족 하도록 합니다.

 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/cpp/FxCop.Design.OneDimensionForIndexer.cpp#1)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/cs/FxCop.Design.OneDimensionForIndexer.cs#1)]
 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/vb/FxCop.Design.OneDimensionForIndexer.vb#1)]

## <a name="related-rules"></a>관련된 규칙
 [CA1043: 인덱서에 정수 또는 문자열 인수를 사용하십시오.](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

 [CA1024: 적합한 속성을 사용하십시오.](../code-quality/ca1024-use-properties-where-appropriate.md)



