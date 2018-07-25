---
title: JavaScript 언어 참조 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.General
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript
ms.assetid: 1c457e66-a6b2-4545-b2dd-33a59d8661e8
caps.latest.revision: 62
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 981e04d94ac803c76705cd7014f5d29721188512
ms.sourcegitcommit: c842955aa9ee9f149bb63e66e46c5c29be6e9881
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36962660"
---
# <a name="javascript-language-reference"></a>JavaScript 언어 참조
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 는 웹 페이지 및 기타 응용 프로그램에 포함할 수 있는 스크립트 언어입니다.  
  
 이 설명서는 ECMAScript 언어 사양(5번째 버전)과 호환되는 JavaScript의 Microsoft 구현에 대해 설명합니다. 또한 ECMA 표준에 포함되어 있지 않은 추가 기능도 제공합니다.  

> [!NOTE]
> 모든 Microsoft의 JavaScript API 참조(500개 이상의 페이지)를 docs.microsoft.com에서 MDN 사본으로 리디렉션하여 [MDN 웹 문서](https://developer.mozilla.org/en-US/)를 웹의 원스톱, 초연 개발 리소스로 만들려는 커뮤니티 차원의 노력에 동참하였습니다. 자세한 내용은 이 [공지](https://blogs.windows.com/msedgedev/2018/06/26/chakra-docs-mdn-web-docs/)를 참조하세요.
  
 HTML 및 브라우저 개체를 나타내는 HTML, CSS 및 DOM(문서 개체 모델)과 함께 브라우저 응용 프로그램에서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드를 사용할 수 있습니다.  
  
-   HTML에 대한 자세한 내용은 [HTML/XHTML 참조](http://go.microsoft.com/fwlink/p/?LinkId=251007)를 참조하세요.  
  
-   CSS에 대한 자세한 내용은 [CSS 스타일시트](http://go.microsoft.com/fwlink/p/?LinkId=251008)를 참조하세요.  
  
-   DOM에 대한 자세한 내용은 [DOM(문서 개체 모델)](http://go.microsoft.com/fwlink/p/?LinkId=251009)을 참조하세요.  
  
 [!INCLUDE[win8](../javascript/includes/win8-md.md)]와 [!INCLUDE[win81](../javascript/includes/win81-md.md)]에서 실행되는 Windows 스토어 앱 및 Windows 10에서 실행되는 UWP(유니버설 Windows 플랫폼) 앱에서도 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드를 사용할 수 있습니다. Windows 스토어 앱은 [!INCLUDE[vs_dev11_long](../javascript/includes/vs-dev11-long-md.md)], [!INCLUDE[vs_dev12](../javascript/includes/vs-dev12-md.md)] 및 [!INCLUDE[vs_dev14](../javascript/includes/vs-dev14-md.md)]에서 개발할 수 있고 UWP 앱은 [!INCLUDE[vs_dev14](../javascript/includes/vs-dev14-md.md)]에서 개발할 수 있습니다.  
  
-   [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] 앱의 JavaScript에 대한 자세한 내용은 [JavaScript 로드맵](https://msdn.microsoft.com/en-us/library/windows/apps/hh465037.aspx)을 참조하세요.  
  
-   [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] 앱의 HTML 및 CSS에 대한 자세한 내용은 [Windows 스토어 앱용 HTML/CSS](http://go.microsoft.com/fwlink/p/?LinkId=250939)를 참조하세요.  
  
-   Windows 런타임 및 JavaScript용 Windows 라이브러리 API에 대한 자세한 내용은 [Windows 런타임 및 JavaScript용 Windows 라이브러리의 API 참조](http://go.microsoft.com/fwlink/p/?LinkID=250938)를 참조하세요.  
  
-   JavaScript와 함께 Windows 런타임 API를 사용하는 방법에 대한 자세한 내용은 [Using the Windows Runtime in JavaScript](../jswinrt/using-the-windows-runtime-in-javascript.md)을 참조하세요.  
  
 Visual Studio의 JavaScript 편집기는 IntelliSense를 지원합니다. 자세한 내용은 [JavaScript IntelliSense](http://go.microsoft.com/fwlink/p/?LinkId=256499)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문서 개체 모델](http://go.microsoft.com/fwlink/?LinkId=148095)