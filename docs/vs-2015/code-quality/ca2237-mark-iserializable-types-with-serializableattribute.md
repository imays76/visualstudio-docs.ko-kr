---
title: 'CA2237: ISerializable 형식을 SerializableAttribute로 표시 | Microsoft Docs'
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
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d2bcbca460c404a977b2172f17dfe98164dd52bf
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47592259"
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2237: SerializableAttribute로 ISerializable 형식 표시](https://docs.microsoft.com/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)합니다.

|||
|-|-|
|TypeName|MarkISerializableTypesWithSerializable|
|CheckId|CA2237|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 외부에서 볼 수 있는 형식이 구현 하는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 형식과 인터페이스로 표시 되지 않으면를 <xref:System.SerializableAttribute?displayProperty=fullName> 특성. 규칙 기본 형식이 직렬화 가능 아닌 파생된 형식을 무시 합니다.

## <a name="rule-description"></a>규칙 설명
 공용 언어 런타임에서 serializable로 인식 되도록을 형식으로 표시 되어야 합니다는 <xref:System.SerializableAttribute> 특성 유형 구현을 통해 사용자 지정 serialization 루틴을 사용 하는 경우에는 <xref:System.Runtime.Serialization.ISerializable> 인터페이스입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 적용 된 <xref:System.SerializableAttribute> 형식 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 응용 프로그램 도메인에서 제대로 작동 하려면 직렬화 가능 해야 하기 때문에 예외 클래스에 대 한이 규칙에서 경고를 표시 하지 마십시오.

## <a name="example"></a>예제
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다. 주석 처리를 제거 합니다 <xref:System.SerializableAttribute> 규칙을 만족 하는 줄 특성입니다.

 [!code-csharp[FxCop.Usage.MarkSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkSerializable/cs/FxCop.Usage.MarkSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkSerializable/vb/FxCop.Usage.MarkSerializable.vb#1)]

## <a name="related-rules"></a>관련된 규칙
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: ISerializable을 올바르게 구현하십시오.](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: serialization 생성자를 안전하게 하십시오.](../code-quality/ca2120-secure-serialization-constructors.md)



