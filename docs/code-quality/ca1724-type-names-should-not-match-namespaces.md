---
title: 'CA1724: 형식 이름은 네임스페이스와 달라야 합니다.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c178558743ca69fb3b62eccaf8164e4b49167ad3
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547570"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: 형식 이름은 네임스페이스와 달라야 합니다.
|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식 이름이 일치 하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 네임 스페이스 이름은 대/소문자를 비교 합니다.

## <a name="rule-description"></a>규칙 설명
 형식 이름은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리에 정의된 네임스페이스의 이름과 같아서는 안 됩니다. 이 규칙을 위반하면 라이브러리의 유용성이 저하될 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이름을 일치 하지 않는 형식 이름을 선택 된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리 네임 스페이스입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 새로운 개발에 알려져 있지 않습니다 시나리오 발생이 규칙에서 경고를 표시 해야 하는 위치입니다. 경고를 표시 하지 않으려면 전에 신중 하 게 하는 방법 라이브러리의 사용자 혼동을 줄 수는 일치 하는 이름별 고려해. 제공 되는 라이브러리에 대 한이 규칙에서 경고를 표시 해야 합니다.