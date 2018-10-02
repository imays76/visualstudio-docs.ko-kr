---
title: ': 연산자 ca2226 대칭 오버 로드가 | Microsoft Docs'
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
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6df4a36dae04dadf61790e7be16834dc0d59bdc0
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591130"
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2226: 연산자에는 대칭 오버 로드가 있어야 합니다.](https://docs.microsoft.com/visualstudio/code-quality/ca2226-operators-should-have-symmetrical-overloads)합니다.

|||
|-|-|
|TypeName|OperatorsShouldHaveSymmetricalOverloads|
|CheckId|CA2226|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식이 같음 연산자 또는 같지 않음 연산자를 구현하면서 그 반대 연산자를 구현하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 같음 또는 같지 않음은 형식의 인스턴스에 적용 하면서 그 반대 연산자를 정의 되지 않았고 없는 경우가 있습니다. 일반적으로 형식은 같음 연산자의 부정된 값을 반환 하 여 같지 않음 연산자를 구현 합니다.

 C# 컴파일러에이 규칙의 위반에 대 한 오류가 발생 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 같음 및 같지 않음 연산자를 구현 하거나 존재 하는 것을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다. 형식을 일치 하는 방식으로 작동 하지 것입니다는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)



