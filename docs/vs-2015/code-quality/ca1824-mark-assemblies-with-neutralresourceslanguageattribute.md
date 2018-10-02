---
title: 'CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시 | Microsoft Docs'
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
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d433208e9bb63d770feb00f7f659c9e469a0c4e9
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591298"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시](https://docs.microsoft.com/visualstudio/code-quality/ca1824-mark-assemblies-with-neutralresourceslanguageattribute)합니다.

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 포함 된 어셈블리를 **ResX**-리소스를 따르지만 없는 <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> 적용 합니다.

## <a name="rule-description"></a>규칙 설명
 합니다 **NeutralResourcesLanguage** 특성을 **ResourceManager** 는 어셈블리의 중립 문화권의 리소스를 표시 하는 데 사용 된 언어의 합니다. 중립 리소스 언어와 같은 문화권의 리소스를 조회 하는 경우는 **ResourceManager** 자동으로 주 어셈블리에 있는 리소스를 사용 합니다. 현재 스레드에 대 한 현재 사용자 인터페이스 문화권을 위성 어셈블리를 검색 하지는 않습니다. 이렇게 하면 로드한 첫 리소스에 대한 찾기 성능을 향상시킬 수 있으며 작업이 간단해집니다.

## <a name="fixing-violations"></a>위반 문제 해결
 이 규칙 위반 문제를 해결 하려면 어셈블리에 특성을 추가 하 고 언어 중립 문화권의 리소스를 지정 합니다.

## <a name="specifying-the-language"></a>언어를 지정합니다.

#### <a name="to-specify-the-language-of-the-resource-of-the-neutral-culture"></a>중립 문화권의 리소스의 언어를 지정 하려면

1.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.

2.  왼쪽된 탐색 모음에서 선택 **응용 프로그램**를 클릭 하 고 **어셈블리 정보**합니다.

3.  **어셈블리 정보** 대화 상자에서 언어를 선택 합니다 **중립 언어** 드롭 다운 목록.

4.  **확인**을 클릭합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서 경고를 표시 하지 않을 것입니다. 그러나 시작 성능이 저하 될 수 있습니다.



