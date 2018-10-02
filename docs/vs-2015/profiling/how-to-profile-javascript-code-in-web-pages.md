---
title: '방법: 웹 페이지에서 JavaScript 코드 프로파일링 | Microsoft 문서'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript performance profiling
- Profiling Tools,JavaScript
- web site performance profiling
ms.assetid: 37d02aad-ca4d-4eb0-bf66-ca3ecef31fbe
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a54321b835cad9f37983a386c93f46e26bbdd5ff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552834"
---
# <a name="how-to-profile-javascript-code-in-web-pages"></a>방법: 웹 페이지에서 JavaScript 코드 프로파일링
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 웹 페이지의 JavaScript 코드 프로 파일링](https://docs.microsoft.com/visualstudio/profiling/how-to-profile-javascript-code-in-web-pages)합니다.  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로파일링 도구는 계측 프로파일링 방법을 사용하여 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 웹 응용 프로그램, 임의 웹 페이지 또는 JavaScript 응용 프로그램에서 실행되는 JavaScript 코드에 대한 성능 데이터를 수집할 수 있습니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
-   Internet Explorer 8 이상.  
  
> [!WARNING]
>  Windows 스토어 응용 프로그램에서 JavaScript를 프로파일링하려면 다음 항목 중 하나를 참조하십시오.  
>   
>  -   [JavaScript 함수 타이밍](http://msdn.microsoft.com/library/b2bf49fc-aea7-4d9c-8fcf-cff8b8dd0c03) [원격 장치에서 JavaScript 함수 타이밍](http://msdn.microsoft.com/library/d78812b6-a97e-46dc-8d99-e724d1d725d8)  
> -   [JavaScript 함수 타이밍 데이터 분석](http://msdn.microsoft.com/library/b5aea8d8-36df-47ba-a7ca-95406700ca9b)  
> -  
  
 프로파일링 마법사를 사용하여 성능 세션을 만들 수 있습니다. 계측 방법을 지정한 다음 성능 세션에 대한 속성 대화 상자의 계측 페이지에서 JavaScript 프로파일링 옵션을 지정합니다.  
  
 JavaScript 프로파일링을 지정하면 브라우저에서 실행되는 JavaScript 코드 및 서버에서 실행되는 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 코드가 둘 다 프로파일링됩니다.  
  
-   [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 웹 응용 프로그램의 경우 브라우저에서 실행되는 JavaScript 코드 및 서버에서 실행되는 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 코드가 둘 다 프로파일링됩니다.  
  
-   임의 웹 페이지의 경우 브라우저에서 실행되는 JavaScript 코드가 프로파일링됩니다.  
  
### <a name="to-profile-javascript-in-an-aspnet-web-application-project"></a>ASP.NET 웹 응용 프로그램 프로젝트에서 JavaScript를 프로파일링하려면  
  
1.  [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)]에서 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 웹 프로젝트를 엽니다.  
  
2.  **분석** 메뉴에서 **성능 마법사 시작**을 클릭합니다.  
  
3.  성능 마법사의 첫 페이지에서 **계측** 프로 파일링 방법을 지정하고 **다음**을 클릭합니다.  
  
4.  마법사의 두 번째 페이지에서 현재 프로젝트가 대상 목록에서 선택되었는지 확인하고 **다음**을 클릭합니다.  
  
5.  마법사의 세 번째 페이지에서 **JavaScript 프로파일링** 확인란을 선택하고 **다음**을 클릭합니다.  
  
6.  마법사의 네 번째 페이지에서 **마침** 을 클릭하여 브라우저에서 웹 응용 프로그램을 시작합니다.  
  
7.  프로파일링하려는 기능을 실행합니다.  
  
8.  프로파일링 세션을 종료하려면 브라우저를 닫습니다.  
  
### <a name="to-profile-javascript-in-individual-web-pages-or-a-javascript-applications"></a>개별 웹 페이지 또는 JavaScript 응용 프로그램에서 JavaScript를 프로파일링하려면  
  
1.  [!INCLUDE[vsPreShort](../includes/vspreshort-md.md)]를 엽니다.  
  
2.  **분석** 메뉴에서 **성능 마법사 시작**을 클릭합니다.  
  
3.  성능 마법사의 첫 페이지에서 **계측** 프로 파일링 방법을 지정하고 **다음**을 클릭합니다.  
  
4.  마법사의 두 번째 페이지에서 ASP.NET 또는 JavaScript 응용 프로그램을 클릭한 후 **다음**을 클릭합니다.  
  
5.  마법사의 세 번째 페이지에서 다음을 수행합니다.  
  
    1.  **응용 프로그램을 실행할 URL 또는 경로** 상자에 페이지의 URL을 입력합니다.  
  
    2.  **JavaScript 프로파일링** 확인란을 선택하고 **다음**을 클릭합니다.  
  
6.  마법사의 네 번째 페이지에서 **마침** 을 클릭하여 브라우저에서 웹 페이지를 시작합니다.  
  
7.  프로파일링하려는 기능을 실행합니다.  
  
8.  프로파일링 세션을 종료하려면 브라우저를 닫습니다.



