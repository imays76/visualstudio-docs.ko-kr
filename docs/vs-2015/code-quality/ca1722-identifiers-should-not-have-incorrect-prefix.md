---
title: ': Ca1722 식별자에는 올바른 접두사를 사용 해야 합니다. | Microsoft Docs'
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
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 83843a7713adf3d0c3680470df05bb378c797d38
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591978"
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: 식별자에는 올바른 접두사를 사용해야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1722: 식별자에는 잘못 된 접두사를 사용 해야 합니다.](https://docs.microsoft.com/visualstudio/code-quality/ca1722-identifiers-should-not-have-incorrect-prefix)합니다.

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|
|CheckId|CA1722|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 식별자에 잘못 된 접두사가 있습니다.

## <a name="rule-description"></a>규칙 설명
 규칙에 따라 특정 프로그래밍 요소에만 특정 접두사로 시작하는 이름을 사용할 수 있습니다.

 형식 이름에는 특정 접두사에 있지 않은 및 없습니다 접두사로 'C'와 야 합니다. 이 규칙 위반 'CMyClass' 같은 형식 이름에 대 한 보고 하 고 '캐시가' 같은 형식 이름에 대 한 위반을 보고 하지 않습니다.

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 대 한 필수 항목이 며 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 증가 하는 학습 곡선을 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 식별자에서 접두사를 제거 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)



