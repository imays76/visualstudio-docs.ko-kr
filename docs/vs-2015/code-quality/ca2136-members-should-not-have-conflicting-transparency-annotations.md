---
title: 'CA2136: 멤버 없습니다 충돌 하는 투명도 주석을 가져서는 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f524197fe647e148283e351924701ce7b11c4722
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49894887"
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: 멤버는 충돌하는 투명도 주석을 가져서는 안 됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 형식 멤버는 표시 하는 경우이 규칙이 실행 된 <xref:System.Security> 보안 특성을 멤버의 컨테이너는 다른 투명도 있는 보안 특성.

## <a name="rule-description"></a>규칙 설명
 투명성 특성은 큰 범위의 코드 요소에서 작은 범위의 요소에 적용됩니다. 범위가 큰 코드 요소의 투명성 특성은 첫 번째 요소에 포함된 코드 요소의 투명성 특성보다 우선합니다. 예를 들어로 표시 된 클래스는 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시 되는 메서드를 포함할 수 없습니다는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 위반을 해결 하려면 하위 범위를 갖는 코드 요소에서 보안 특성을 제거 하거나 포함 하는 코드 요소와 동일 하 게 특성을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 표시 하지 마십시오.

## <a name="example"></a>예제
 다음 예제에서는 메서드가 사용 하 여 표시 되는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성 되며로 표시 된 클래스의 멤버는 <xref:System.Security.SecurityCriticalAttribute> 특성입니다. 보안 안전 하 게 특성을 제거 해야 합니다.

 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2136.transparencyannotationsshouldnotconflict/cs/ca2136 - transparencyannotationsshouldnotconflict.cs#1)]



