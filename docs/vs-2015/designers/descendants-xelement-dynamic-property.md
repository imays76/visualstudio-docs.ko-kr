---
title: 하위 항목(XElement 동적 속성) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 29f73bb664e9664ac2a3c56942c86949c9e2bba2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542758"
---
# <a name="descendants-xelement-dynamic-property"></a>하위 항목(XElement 동적 속성)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Descendants (XElement 동적 속성)](https://docs.microsoft.com/visualstudio/designers/descendants-xelement-dynamic-property)합니다.  
  
지정한 확장된 이름과 일치하는 현재 요소의 하위 요소를 모두 검색하는 데 사용되는 인덱서를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
elem.Descendants[{namespaceName}localName]  
```  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `IEnumerable<XElement> Item(String expandedName)` 형식의 인덱서입니다. 이 인덱서는 지정된 하위 요소의 확장된 이름을 사용하여 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 컬렉션에서 일치하는 자식 요소를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 속성은 <xref:System.Xml.Linq.XContainer.Descendants%28System.Xml.Linq.XName%29?displayProperty=fullName> 클래스의 <xref:System.Xml.Linq.XContainer> 메서드와 동일합니다.  
  
 반환된 컬렉션의 요소는 XML 소스 문서 순서로 되어 있습니다.  
  
 이 속성은 지연된 실행을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAttribute 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)   
 [요소](../designers/elements-xelement-dynamic-property.md)



