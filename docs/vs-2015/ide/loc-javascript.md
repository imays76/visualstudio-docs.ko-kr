---
title: '&lt;loc&gt; (JavaScript) | Microsoft Docs'
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
- <loc> JavaScript XML tag
- loc JavaScript XML tag
ms.assetid: 0d3349b6-4bdd-418f-bc11-73665305baae
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7ae2e4459a0da2dbcd096869cf49687c84a68b6c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553925"
---
# <a name="ltlocgt-javascript"></a>&lt;loc&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Visual Studio 2017 설명서](https://docs.microsoft.com/en-us/visualstudio/)합니다.  
  
지역화 된 IntelliSense 정보를 제공 하는 사이드카 파일의 종류와 위치를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<loc filename="filename"  
    format="vsdoc|messagebundle" />  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 선택 사항입니다. 중립 문화권에 대 한 지역화 정보를 포함 하는 사이드카 파일의 루트 이름입니다. Visual Studio 지역화 정보를 검색 하면이 파일의 문화권 관련 버전을 찾으려고 시도 합니다. 예를 들어 경우 `filename` jquery.xml, 포함 된.js 파일을 동일한 위치에 올바른 문화권별 폴더 (예: JA)에 대 한 Visual Studio 검색 되는 `<loc>` 요소입니다. 문화권별 폴더를 찾은 경우 jquery.xml 파일에 있는지 여부를 확인 합니다. 올바른 파일을 찾을 수 없습니다. 대신 관리 되는 리소스 위치 규칙을 사용 합니다. 에 대 한 기본값 `filename` 대신.js 확장명이.xml 인 하지만 현재 파일의 이름입니다.  
  
 `format`  
 선택 사항입니다. 지역화에 사용 되는 사이드카 파일의 형식입니다. 사용 하 여 `messagebundle` 열기 Ajax 메타 데이터에서 정의한 메시지 번들의 사용을 지정 합니다. `messagebundle` 권장 되는 형식이입니다. 그러나이 형식은.winmd 파일 또는 Microsoft Ajax에서 지원 되지 않습니다. 사용 하 여 `vsdoc` Ajax 및 Windows 런타임에서 사용 되는 표준.NET Framework 지역화 형식을 지정 합니다. 이 특성은 선택적 요소입니다. `vsdoc` 기본 형식이입니다.  
  
## <a name="remarks"></a>설명  
 합니다 `<loc>` 요소와 동일한 섹션에 있는 파일의 위쪽에 표시 되어야 합니다는 `<reference>` 요소입니다. 사용에 대 한 규칙을 `<loc>` 요소와 동일 합니다 `<reference>` 요소입니다. 자세한 내용은의 "참조 지시문" 섹션을 참조 하세요 [JavaScript IntelliSense](../ide/javascript-intellisense.md)합니다.  
  
 Visual Studio 처리는 단일 `<loc>` 각.js 파일에 대 한 요소입니다. 여러 `<loc>` 요소가 있는 단일 `<loc>` 요소를 사용 합니다. 결정에 대 한 동작 `<loc>` 사용 하는 요소에 정의 되어 있지 않습니다.  
  
 메시지 번들 형식을 사용 하는 경우 사용 합니다 `locid` XML 문서 주석에 지정 하는 특성을 `name` 특성 값.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다는 `<loc>` messagebundle 형식 요소입니다. MessageFilename.xml 라는 파일에 다음 XML을 추가 하 고 설명에 지정 된 대로 올바른 문화권별 폴더에 파일을 배치 합니다 `filename` 매개 변수입니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<messagebundle>  
  <msg name="1">A class that represents a rectangle</msg>  
  <msg name="2">The height of a rectangle</msg>  
  <msg name="3">The width of a rectangle</msg>  
</messagebundle>  
  
```  
  
 Messagebundle 예를 들어 프로젝트에서 JavaScript 파일에 다음 코드를 추가 합니다. `<loc>` 요소는 JavaScript 파일에 첫 번째 줄으로 표시 되어야 합니다. 이 코드의 설명에 사용 가능한 경우 지역화 된 설명으로 바뀝니다.  
  
```javascript  
/// <loc filename="messageFilename.xml" format="messagebundle"/>  
  
function doSomething(a,b)   
{  
    /// <summary locid='1'>description</summary>  
    /// <param name='a' locid='2'>parameter a description</param>  
    /// <param name='b' locid='3'>parameter b description</param>  
}  
  
```  
  
 다음 예제는 VSDoc 형식을 사용합니다. ScriptFilename.xml 라는 파일에 다음 XML을 추가 하 고 올바른 문화권별 폴더에 파일을 배치 합니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<doc>  
  <assembly>  
    <name>Lights</name>  
  </assembly>  
  <members>  
    <member name="M:illuminate">  
      <summary>Activates a light. </summary>  
      <param name='a'>The light to activate. </param>  
    </member>  
  </members>  
</doc>  
  
```  
  
 VSDoc 예를 들어 프로젝트에서 JavaScript 파일에 다음 코드를 추가 합니다. 이 코드의 설명에 사용 가능한 경우 지역화 된 설명으로 바뀝니다.  
  
```javascript  
/// <loc filename="scriptFilename.xml" format="vsdoc" />  
  
function illuminate(a)   
{  
    /// <summary locid='M:illuminate'>description</summary>  
    /// <param name='a' type='Number'>parameter a description</param>  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)



