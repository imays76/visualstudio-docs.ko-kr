---
title: XML 코드 조각 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bae360d1aea43006138397b3bed2857a2b1dad59
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564603"
---
# <a name="xml-snippets"></a>XML 조각
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [XML 조각](https://docs.microsoft.com/visualstudio/xml-tools/xml-snippets)합니다.  
  
  
XML 편집기 기능 이라는 기능을 제공 *XML 조각*, XML 파일을 보다 신속 하 게 만들 수 있습니다. XML 조각을 파일에 삽입하면 이 XML 조각을 다시 사용할 수 있습니다. XSD(XML 스키마 정의 언어) 스키마를 기반으로 XML 데이터를 생성할 수도 있습니다.  
  
## <a name="reusable-xml-snippets"></a>다시 사용할 수 있는 XML 조각  
 XML 편집기에는 몇 가지 일반 작업을 포괄하는 많은 조각이 포함되어 있습니다. 이 조각을 사용하여 XML 파일을 더욱 쉽게 만들 수 있습니다. 예를 들어, XML 스키마를 만드는 경우 "복합 형식 시퀀스 요소" 및 "단순 형식 요소" 조각을 사용하면 다음 XML 텍스트가 파일에 삽입됩니다. 그러면 필요에 맞게 `name` 값을 변경할 수 있습니다.  
  
```  
<xs:element name="name">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="name">  
        <xs:simpleType>  
          <xs:restriction base="xs:string"></xs:restriction>  
        </xs:simpleType>  
      </xs:element>  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 두 가지 방법으로 조각을 삽입할 수 있습니다. 합니다 **코드 조각 삽입** 명령은 커서 위치에서 XML 조각을 삽입 합니다. 합니다 **감싸기** 명령을 선택한 텍스트 주위의 XML 조각을 래핑합니다. 두 명령을 사용할 수 있습니다에서 합니다 **IntelliSense** 아래에 하위 메뉴가 합니다 **편집** 메뉴에서 또는 편집기 바로 가기 메뉴에서.  
  
 자세한 내용은 [방법: 사용 하 여 XML 조각](../xml-tools/how-to-use-xml-snippets.md)합니다.  
  
## <a name="schema-generated-xml-snippets"></a>스키마에 의해 생성된 XML 조각  
 XML 편집기에서는 XML 스키마에서 XML 조각을 생성할 수 있는 기능을 제공합니다. 이 기능을 사용하면 요소의 스키마 정보에서 생성된 XML 요소로 해당 요소를 채울 수 있습니다.  
  
 자세한 내용은 [방법: XML 조각에서 an XML 스키마를 생성할](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)합니다.  
  
## <a name="create-new-xml-snippets"></a>새 XML 조각 만들기  
 기본적으로 [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Studio에 포함된 조각 외에도 사용자가 직접 XML 조각을 만들어 사용할 수 있습니다.  
  
 자세한 내용은 [방법: XML 조각 만들기](../xml-tools/how-to-create-xml-snippets.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 편집기](../xml-tools/xml-editor.md)



