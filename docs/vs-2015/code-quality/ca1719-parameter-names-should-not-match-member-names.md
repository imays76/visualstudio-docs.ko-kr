---
title: ': 매개 변수 이름은 ca1719 멤버 이름 | Microsoft Docs'
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
- ParameterNamesShouldNotMatchMemberNames
- CA1719
helpviewer_keywords:
- CA1719
- ParameterNamesShouldNotMatchMemberNames
ms.assetid: c6fea690-1659-4ee7-a1c5-125ad6754525
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7a80b173cb17f5ce8f946ad2adb32cde43159141
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591136"
---
# <a name="ca1719-parameter-names-should-not-match-member-names"></a>CA1719: 매개 변수 이름은 멤버 이름과 달라야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1719: 매개 변수 이름은 멤버 이름과 달라 해야](https://docs.microsoft.com/visualstudio/code-quality/ca1719-parameter-names-should-not-match-member-names)합니다.

|||
|-|-|
|TypeName|ParameterNamesShouldNotMatchMemberNames|
|CheckId|CA1719|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 외부에서 볼 수 있는 멤버 이름의 대/소문자 구분 비교에서 해당 매개 변수 중 하나의 이름 일치합니다.

## <a name="rule-description"></a>규칙 설명
 매개 변수 이름은 매개 변수의 의미를 나타내고 멤버 이름은 멤버의 의미를 나타내야 합니다. 매개 변수와 멤버의 의미가 같게 디자인되는 경우는 드뭅니다. 매개 변수의 이름을 멤버 이름과 동일하게 지정하는 것은 비직관적이고 라이브러리 사용을 어렵게 만듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 멤버 이름과 일치 하지 않는 매개 변수 이름을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 새로운 개발에 알려져 있지 않습니다 시나리오 발생이 규칙에서 경고를 표시 해야 하는 위치입니다. 제공 되는 라이브러리에 대 한이 규칙에서 경고를 표시 해야 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

 [CA1707: 식별자에는 밑줄을 사용할 수 없습니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)



