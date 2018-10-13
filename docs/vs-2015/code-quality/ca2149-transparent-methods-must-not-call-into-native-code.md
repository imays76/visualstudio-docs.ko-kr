---
title: 'CA2149: 투명 한 메서드 호출 해서는 네이티브 코드로 | Microsoft Docs'
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
- CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3e048bd5e85388fcccf54a4a48d81acfb6cc66b3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208834"
---
# <a name="ca2149-transparent-methods-must-not-call-into-native-code"></a>CA2149: 투명한 메서드는 네이티브 코드를 호출해서는 안 됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|TransparentMethodsMustNotCallNativeCode|
|CheckId|CA2149|
|범주|Microsoft.Security|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 메서드는 메서드 스텁 P/Invoke 등을 통해 네이티브 함수를 호출합니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙은 P/Invoke를 통해 네이티브 코드를 직접 호출하는 모든 투명 메서드에 적용됩니다. 이 규칙 위반을 <xref:System.MethodAccessException> 수준 2 투명성 모델에 대 한 완전 요청이 <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> 수준 1 투명성 모델에서.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 사용 하 여 네이티브 코드를 호출 하는 메서드를 표시 합니다 <xref:System.Security.SecurityCriticalAttribute> 또는 <xref:System.Security.SecuritySafeCriticalAttribute> 특성입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 [!code-csharp[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2149.transparentmethodsmustnotcallnativecode/cs/ca2149 - transparentmethodsmustnotcallnativecode.cs#1)]



