---
title: 'CA2130: 보안 위험 상수는 투명 해야 | Microsoft Docs'
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
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a74d6fe3c0507914fa4bd9723a53579db230c467
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591592"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: 보안 위험 상수는 투명해야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2130: 보안 위험 상수는 투명 해야 합니다.](https://docs.microsoft.com/visualstudio/code-quality/ca2130-security-critical-constants-should-be-transparent)합니다.

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 상수 필드 또는 열거형 멤버를 사용 하 여 표시 되어 여 <xref:System.Security.SecurityCriticalAttribute>입니다.

## <a name="rule-description"></a>규칙 설명
 런타임에 조회가 필요하지 않도록 컴파일러에서 상수 값을 인라인하기 때문에 상수 값에 투명성이 적용되지 않습니다. 상수 필드는 보안 투명해야 하므로 코드 검토자는 투명 코드가 상수에 액세스할 수 없다고 가정하지 않습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하는 필드 또는 값에서 SecurityCritical 특성을 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 열거형 값 `EnumWithCriticalValues.CriticalEnumValue` 상수의 `CriticalConstant` 이 경고가 발생 합니다. 문제를 해결 하려면 제거를 [`SecurityCritical`] 특성 수 있도록 보안 투명 합니다.

 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2130.constantsshouldbetransparent/cs/ca2130 - constantsshouldbetransparent.cs#1)]



