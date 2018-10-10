---
title: '&lt;요약&gt; (JavaScript) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- summary JavaScript XML tag
- <summary> JavaScript XML tag
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f6b4808112e746e30f0e40d4626f546c3f99b193
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48879020"
---
# <a name="ltsummarygt-javascript"></a>&lt;요약&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Visual Studio 2017 설명서](/visualstudio/)합니다.  
  
함수 또는 메서드에 대한 설명을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<summary locid="descriptionID">description  
</summary>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `locid`  
 선택 사항입니다. 메서드나 함수에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 요소입니다.  
  
 `description`  
 선택 사항입니다. 함수 또는 메서드의 설명입니다.  
  
## <a name="remarks"></a>설명  
 함수를 포함 하는 주석을 추가 하는 데 필요한 요소 [ \<요약 >](../ide/summary-javascript.md)합니다 [ \<param >](../ide/param-javascript.md), 및 [ \<반환 >](../ide/returns-javascript.md), 함수 본문은 문 앞에 배치 되어야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다는 `<summary>` 요소입니다.  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when supplied a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)



