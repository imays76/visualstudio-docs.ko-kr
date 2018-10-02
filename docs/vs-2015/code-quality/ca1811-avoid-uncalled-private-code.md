---
title: ': Ca1811 호출 되지 않는 개인 코드 | Microsoft Docs'
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
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2f08d3fe31d6a314de9bc64441add64246f8e256
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591994"
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1811: 호출 되지 않는 전용 코드를 방지](https://docs.microsoft.com/visualstudio/code-quality/ca1811-avoid-uncalled-private-code)합니다.

|||
|-|-|
|TypeName|AvoidUncalledPrivateCode|
|CheckId|CA1811|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Private 또는 internal (어셈블리 수준) 멤버 어셈블리의 호출자가 없는, 공용 언어 런타임에 의해 호출 되지 않습니다 및 대리자에 의해 호출 되지 않습니다. 이 규칙에 의해 다음 멤버를 확인 하지 않습니다.

-   명시적 인터페이스 멤버입니다.

-   정적 생성자입니다.

-   Serialization 생성자입니다.

-   로 표시 된 메서드 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>합니다.

-   재정의 된 멤버입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 거짓 긍정 진입점 발생 하는 경우 현재에서 식별할 수 없는 규칙 논리를 보고할 수 있습니다. 또한 컴파일러는 어셈블리에 호출 되지 않는 코드를 내보낼 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하 고, 호출 되지 않는 코드를 제거 하 고 또는 호출 하는 코드를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)



