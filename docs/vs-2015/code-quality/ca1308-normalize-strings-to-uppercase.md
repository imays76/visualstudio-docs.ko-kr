---
title: 'CA1308: 문자열을 대문자로 정규화 하십시오. | Microsoft Docs'
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
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0fce05563f00110ab4e1d21a52f100d0f01568e4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49846280"
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: 문자열을 대문자로 정규화하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|NormalizeStringsToUppercase|
|CheckId|CA1308|
|범주|Microsoft.Globalization|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 작업에서 문자열을 소문자로 정규화합니다.

## <a name="rule-description"></a>규칙 설명
 문자열은 대문자로 정규화되어야 합니다. 작은 그룹 문자를 소문자로 변환 되는 왕복을 만들 수 없습니다 경우입니다. 문자 변환 한 로캘에서 다른 로캘로 문자 데이터를 다르게 표시 하 고 정확 하 게 하는 방법을 라운드트립 하려면 변환된 된 문자에서 원래 문자를 검색 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 변경 작업 문자열 변환 되도록 문자열을 소문자로 변환 하는 대신 대문자로 합니다. 예를 들어, `String.ToLower(CultureInfo.InvariantCulture)`를 `String.ToUpper(CultureInfo.InvariantCulture)`로 변경합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 결과 (예: UI에 표시 하는 경우)를 기반으로 보안을 결정 하지 않는 경우 경고 메시지를 표시 하지 않으려면 안전 합니다.

## <a name="see-also"></a>참고 항목
 [전역화 경고](../code-quality/globalization-warnings.md)



