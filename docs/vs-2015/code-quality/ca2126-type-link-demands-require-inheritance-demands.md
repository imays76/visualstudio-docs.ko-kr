---
title: 'CA2126: 형식 링크 요청 상속 요청이 필요 | Microsoft Docs'
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
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
helpviewer_keywords:
- CA2126
- TypeLinkDemandsRequireInheritanceDemands
ms.assetid: 07b604e5-5579-4df9-a578-dadd0d8370a7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3f482350517858fffc74600c3743a22192aa6a49
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591730"
---
# <a name="ca2126-type-link-demands-require-inheritance-demands"></a>CA2126: 형식 링크 요청에는 상속 요청이 필요합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2126: 형식 링크 요청에는 상속 요청이 필요](https://docs.microsoft.com/visualstudio/code-quality/ca2126-type-link-demands-require-inheritance-demands)합니다.

|||
|-|-|
|TypeName|TypeLinkDemandsRequireInheritanceDemands|
|CheckId|CA2126|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 보호 되는 public unsealed 형식이 링크 요청을 사용 하 여 재정의 가능한 메서드가 및 형식이 나 메서드를 모두 상속 요청으로 보호 됩니다.

## <a name="rule-description"></a>규칙 설명
 메서드 또는 해당 선언 형식 링크 요청을 직접 실행 호출자 메서드의 지정 된 권한이 필요 합니다. 메서드에 대 한 상속 요청 재정의 메서드는 지정 된 권한이 필요 합니다. 형식에 대 한 상속 요청 파생 클래스에 지정 된 권한이 필요 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 형식 또는 메서드가 링크 요청으로 동일한 권한에 대 한 상속 요청으로 보호 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다.

 [!code-cpp[FxCop.Security.TypesWithLinkDemands#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/cpp/FxCop.Security.TypesWithLinkDemands.cpp#1)]
 [!code-csharp[FxCop.Security.TypesWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/cs/FxCop.Security.TypesWithLinkDemands.cs#1)]
 [!code-vb[FxCop.Security.TypesWithLinkDemands#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.TypesWithLinkDemands/vb/FxCop.Security.TypesWithLinkDemands.vb#1)]

## <a name="related-rules"></a>관련된 규칙
 [CA2108: 값 형식에서 선언적 보안을 검토하십시오.](../code-quality/ca2108-review-declarative-security-on-value-types.md)

 [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

 [CA2122: 링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)

 [CA2123: 재정의 링크 요청은 기본 형식의 링크 요청과 같아야 합니다.](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)

## <a name="see-also"></a>참고 항목
 [보안 코딩 지침](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) [상속 요청이](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9) [링크 요청](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) [요구](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48)



