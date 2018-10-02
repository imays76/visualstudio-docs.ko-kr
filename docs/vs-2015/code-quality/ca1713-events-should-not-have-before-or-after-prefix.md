---
title: ': 이벤트 ca1713 before 또는 after 접두사 | Microsoft Docs'
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
- EventsShouldNotHaveBeforeOrAfterPrefix
- CA1713
helpviewer_keywords:
- CA1713
- EventsShouldNotHaveBeforeOrAfterPrefix
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 46ed0ad62d145b7c60c9f20e1a3770016098a236
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591227"
---
# <a name="ca1713-events-should-not-have-before-or-after-prefix"></a>CA1713: 이벤트에 Before 또는 After 접두사를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1713: 이벤트 before 또는 after 접두사 없어야](https://docs.microsoft.com/visualstudio/code-quality/ca1713-events-should-not-have-before-or-after-prefix)합니다.

|||
|-|-|
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|
|CheckId|CA1713|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 이벤트의 이름이 'Before' 또는 '사후'로 시작 합니다.

## <a name="rule-description"></a>규칙 설명
 이벤트 이름에는 이벤트를 발생 시키는 작업을 설명 해야 합니다. 특정 시퀀스에서 발생하는 관련 이벤트의 이름을 지정하려면 현재 또는 과거 시제를 사용하여 동작 시퀀스 내의 상대적인 위치를 나타냅니다. 예를 들어, 이벤트 쌍 이름이 발생 하면 리소스를 닫을 때 이름을 지정할 수 있습니다 것 '닫는' 및 '종결' 대신 'BeforeClose' 및 'AfterClose'.

 명명 규칙은 공통 된 모양을 라이브러리에 대 한 해당 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 대 한 필수 항목이 며 관리 코드 개발의 전문 지식을 가진 사람이 라이브러리를 개발 하는 고객 신뢰도 증가 하는 학습 곡선을 줄어듭니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이벤트 이름에서 접두사를 제거 하 고 현재 또는 과거 시제 동사를 사용 하 여 이름을 변경 하는 것이 좋습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.



