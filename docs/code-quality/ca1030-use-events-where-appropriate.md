---
title: 'CA1030: 적절한 경우 이벤트를 사용하세요.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 445330d654e870fe12aa2ca19626377972235eac
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860810"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: 적절한 경우 이벤트를 사용하세요.

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 Public, protected 또는 private 메서드 이름이 다음 중 하나를 사용 하 여 시작합니다.

- 추가 기능

- RemoveOn

- 실행

- raise

## <a name="rule-description"></a>규칙 설명
 이 규칙에서는 보통 이벤트에 사용되는 이름을 갖는 메서드를 찾아냅니다. 이벤트는 관찰자 또는 게시-구독 디자인 패턴에 따라 사용 하면 하나의 개체에서 상태 변경을 다른 개체에 전달 해야 합니다. 명확 하 게 정의 된 상태 변경에 대 한 응답에는 메서드가 호출 되는 경우 이벤트 처리기에서 메서드를 호출 해야 합니다. 메서드를 호출하는 개체는 메서드를 직접 호출하는 대신 이벤트를 발생시켜야 합니다.

 이벤트의 몇 가지 일반적인 예는 사용자 인터페이스 응용 프로그램 단추 클릭과 같은 사용자 작업을 실행할 코드의 세그먼트를 발생 하는 위치에 있습니다. .NET Framework 이벤트 모델에 사용자 인터페이스를 제한 되지 않습니다. 사용 해야 원하는 위치에 하나 이상의 개체 상태가 변경 통신 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 개체의 상태가 변경 될 때 메서드가 호출 되는 경우.NET Framework 이벤트 모델을 사용 하도록 디자인을 변경 하는 것이 좋습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우
 메서드는.NET Framework 이벤트 모델을 사용 하 여 작동 하지 않는 경우이 규칙에서 경고를 표시 합니다.