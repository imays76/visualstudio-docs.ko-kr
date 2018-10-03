---
title: 'CA1726: 기본 설정된 용어를 사용 합니다. | Microsoft Docs'
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
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b13c43a563a158a2eeb8484e29810c5b91d110aa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543322"
---
# <a name="ca1726-use-preferred-terms"></a>CA1726: 기본 설정 용어를 사용하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017에서 최신 설명서를 참조 하세요 [CA1726: 기본 설정된 용어를 사용 하 여](https://docs.microsoft.com/visualstudio/code-quality/ca1726-use-preferred-terms) docs.microsoft.com에서 제공 합니다.  
  
|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|범주|Microsoft.Naming|  
|변경 수준|주요-어셈블리에서 발생 한 경우<br /><br /> 아님-형식 매개 변수에서 발생 한 경우|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 식별자의 이름에 특정 용어가 포함되어 있는데, 이 용어에는 기본 설정된 대체 용어가 있습니다. 또는 이름을 플래그 또는 플래그 용어를 포함합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙 식별자 토큰 구문 분석합니다. 각 토큰 및 각 연속 이중 토큰 조합 및 사용자 지정 사전의 사용 되지 않는 섹션에서 규칙에 기본 제공 되는 용어와 비교 됩니다. 다음 표에서 규칙 및 해당 기본 대안에 내장 된 용어를 보여 줍니다.  
  
|사용 되지 않는 용어|기본 용어|  
|-------------------|--------------------|  
|되지 않습니다.|오지|  
|취소됨|Canceled|  
|수 없음|수 없습니다.|  
|ComPlus|EnterpriseServices|  
|수 없음|CouldNot|  
|Didnt|DidNot|  
|Doesnt|하지 않습니다|  
|Dont|안 함|  
|플래그 또는 플래그|대체 용어가 없는 경우 사용하지 마십시오.|  
|하지|HadNot|  
|되지 않았습니다.|HasNot|  
|아직|HaveNot|  
|인덱스|Indexes|  
|되지 않습니다.|IsNot|  
|로그인|로그온|  
|로그 아웃|로그 오프|  
|Shouldnt|ShouldNot|  
|Sign On|로그인|  
|사인 오프|로그 아웃|  
|Wasnt|WasNot|  
|되지 않았습니다.|WereNot|  
|안 됨|WillNot|  
|Wouldnt|WouldNot|  
|쓰기 가능|쓰기 가능|  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하는 기본 대체 용어를 사용 하 여 용어를 대체 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 식별자의 이름을 의도적인 하는 기본 용어 대신 원래 용어와 특히 관련이 하는 경우에이 규칙에서 경고를 표시 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [이름 지정 경고](../code-quality/naming-warnings.md)

