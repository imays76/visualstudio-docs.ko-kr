---
title: '&lt;사용 되지 않는&gt; (JavaScript) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 220f320eba6231161328a08914848114db7ae02b
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48880471"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;사용 되지 않는&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Visual Studio 2017 설명서](/visualstudio/)합니다.  
  
사용되지 않는 함수 또는 메서드를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<deprecated  
    type="deprecate|remove"  
    locid="descriptionID">description  
</deprecated>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 선택 사항입니다. 향후 릴리스에서 함수 또는 메서드를 제거할 수는 있는지 여부 또는 여부 함수 또는 메서드를 이미 제거 및 용도 오류가 발생할 수 있는지 지정 합니다. 로 `deprecate` 릴리스에서 함수 또는 메서드를 제거할 수를 지정할 수 있습니다. 로 `remove` 함수 또는 메서드를 이미 제거 된 것을 지정 합니다.  
  
 `locid`  
 선택 사항입니다. 메서드나 함수에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 요소입니다.  
  
 `description`  
 선택 사항입니다. 함수 또는 메서드의 사용이 중단 되는 설명입니다.  
  
## <a name="remarks"></a>설명  
 함수를 포함 하는 주석을 추가 하는 데 필요한 요소 `<deprecated>`, 함수 본문은 문 앞에 배치 되어야 합니다. 더 이상 사용 되지 함수를 표시 하면 대체 하는 것이 좋습니다 해당 [ \<요약 >](../ide/summary-javascript.md) 사용 하 여 요소를 `<deprecated>` 요소입니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다는 `<deprecated>` 요소입니다.  
  
```javascript  
function areaFunction(radiusParam) {  
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)



