---
title: 'CA2228: 릴리스되지 않은 리소스 형식을 제공 하지 마십시오. | Microsoft Docs'
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
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 84dc7c20f4109f7d66ed83b22fcec36dacc5eb3f
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591653"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: 릴리스되지 않은 리소스 형식을 제공하지 마십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA2228: 릴리스되지 않은 리소스 형식을 제공 하지 마십시오](https://docs.microsoft.com/visualstudio/code-quality/ca2228-do-not-ship-unreleased-resource-formats)합니다.

|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|범주|Microsoft.Usage|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 리소스 파일의 버전을 사용 하 여 빌드된는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 는 현재 지원 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
 시험판 버전을 사용 하 여 빌드된 리소스 파일을 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 지원 되는 버전의.NET Framework에서 사용할 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 지원 되는 버전을 사용 하 여 리소스를 작성 합니다 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]k.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.



