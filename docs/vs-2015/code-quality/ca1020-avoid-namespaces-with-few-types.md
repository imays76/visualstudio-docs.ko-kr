---
title: 'CA1020: 형식이 사용 하 여 네임 스페이스 방지 | Microsoft Docs'
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
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6663660319791f1e81d0ed89f171c929c3e50725
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906184"
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020: 형식이 부족한 네임스페이스를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidNamespacesWithFewTypes|
|CheckId|CA1020|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 전역 네임 스페이스 이외의 네임 스페이스에는 5 개 미만의 형식을 포함합니다.

## <a name="rule-description"></a>규칙 설명
 각 네임 스페이스에 논리적 구성이 고 밀도가 네임 스페이스에 형식을 배치 하는 유효한 이유가 있는지 확인 합니다. 네임 스페이스에는 대부분의 시나리오에서 함께 사용 되는 형식을 포함 해야 합니다. 응용 프로그램 상호 배타적인 경우 형식 별도 네임 스페이스에 있어야 합니다. 예를 들어, 합니다 <xref:System.Web.UI> 네임 스페이스 웹 응용 프로그램에서 사용 되는 형식을 포함 하며 <xref:System.Windows.Forms> 네임 스페이스에서 사용 되는 형식을 포함 [!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)]-기반 응용 프로그램. 두 네임스페이스에 사용자 인터페이스의 특성을 제어하는 형식이 포함되었더라도 이러한 형식은 동일한 응용 프로그램에서 사용하도록 디자인되지 않았습니다. 따라서 별도의 네임스페이스에 배치됩니다. 기능 검색 기능을 증가 하기 때문에 신중 하 게 네임 스페이스 조직 유용할 수 있습니다. 네임 스페이스 계층을 검사 하 여 라이브러리 소비자 기능을 구현 하는 형식을 찾을 수 있어야 합니다.

> [!NOTE]
>  디자인 타임 형식 및 사용 권한 하지이 지침을 준수 하도록 다른 네임 스페이스에 병합 해야 합니다. 이러한 형식은 각각 자체 네임 스페이스에 기본 네임 스페이스 아래에 속하고 네임 스페이스에서 종료 되어야 `.Design` 고 `.Permissions`, 각각.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 단일 네임 스페이스로 몇 가지 형식이 포함 된 네임 스페이스를 결합 하려고 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 네임 스페이스는 다른 네임 스페이스의 형식과 함께 사용 되는 형식이 포함 되지 않은 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.



