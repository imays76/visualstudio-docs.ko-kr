---
title: 'CA2239: 제공 선택적 필드에 deserialization 메서드 | Microsoft Docs'
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
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 235880285ce80d74fec67e5bcd497f046f3aa842
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591995"
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2239: 제공 선택적 필드에 deserialization 메서드](https://docs.microsoft.com/visualstudio/code-quality/ca2239-provide-deserialization-methods-for-optional-fields)합니다.

|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식으로 표시 된 필드에는 <xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName> 특성 및 형식을 역직렬화 이벤트 처리 메서드를 제공 하지 않습니다.

## <a name="rule-description"></a>규칙 설명
 <xref:System.Runtime.Serialization.OptionalFieldAttribute> 특성 serialization에 영향을 주지 않으면 특성으로 표시 된 필드는 serialize 합니다. 그러나 필드 역직렬화에서 무시 되 고 해당 형식과 연결 된 기본 값을 유지 합니다. Deserialization 프로세스 중에 필드를 설정 하려면 역직렬화 이벤트 처리기를 선언 되어야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 형식에 메서드를 처리 하는 역직렬화 이벤트를 추가 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 필드는 역직렬화 프로세스 중에 무시 되어야 하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예에서는 선택적 필드와 역직렬화 이벤트 형식을 처리 메서드를 보여 줍니다.

 [!code-csharp[FxCop.Usage.OptionalFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OptionalFields/cs/FxCop.Usage.OptionalFields.cs#1)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.OptionalFields/vb/FxCop.Usage.OptionalFields.vb#1)]

## <a name="related-rules"></a>관련된 규칙
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: ISerializable을 올바르게 구현하십시오.](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2120: serialization 생성자를 안전하게 하십시오.](../code-quality/ca2120-secure-serialization-constructors.md)



