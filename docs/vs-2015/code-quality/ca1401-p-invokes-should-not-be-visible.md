---
title: 'CA1401: P-invoke는 노출 되지 | Microsoft Docs'
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
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8c376c2ae8a1d09ff040d9929617c75037ac5d28
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591269"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: P/Invoke는 노출되지 않아야 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1401: P-invoke 표시 되지 않아야](https://docs.microsoft.com/visualstudio/code-quality/ca1401-p-invokes-should-not-be-visible)합니다.

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|범주|Microsoft.Interoperability|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 공용 형식에서 public 또는 protected 메서드는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성 (으로 구현 합니다 `Declare` 키워드 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).

## <a name="rule-description"></a>규칙 설명
 로 표시 되는 메서드를 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성 (또는 사용 하 여 정의 된 메서드를 합니다 `Declare` 키워드 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) 플랫폼 호출 서비스를 사용 하 여 비관리 코드 액세스. 이러한 메서드는 노출되지 않아야 합니다. 이러한 메서드를 private 또는 internal로 유지에서 수 있도록 호출자 그렇지 않으면 호출 하지 못했습니다 관리 되지 않는 Api에 대 한 액세스를 허용 하 여 보안 침해에 라이브러리를 사용할 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 메서드의 액세스 수준을 변경 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 메서드를 선언 합니다.

 [!code-csharp[FxCop.Interoperability.DllImports#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/cs/FxCop.Interoperability.DllImports.cs#1)]
 [!code-vb[FxCop.Interoperability.DllImports#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/vb/FxCop.Interoperability.DllImports.vb#1)]



