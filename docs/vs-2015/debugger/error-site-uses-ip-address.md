---
title: '오류: 사이트에서 IP 주소를 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: b2b8ddc8-746d-46e3-87a6-b956b1ee048d
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: daa9ed74df46dd6be66a27d09cbbd7c311e03de4
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51793674"
---
# <a name="error-site-uses-ip-address"></a>오류: 사이트에서 IP 주소를 사용합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 오류는 디버거에서 IP 주소를 사용하는 웹 응용 프로그램에 자동으로 연결하려고 할 때 발생합니다. 변경 하는 경우 이런 **웹 사이트 id** 하 **특정 IP 주소를 사용 하 여** IIS에서 합니다.  
  
 자동 연결이 제대로 동작하기 위해서는 컴퓨터 이름뿐 아니라 특정 IP 주소도 함께 사용하여 프로젝트를 만들어야 합니다. 그렇지 않으면 디버거에서 컴퓨터 이름을 localhost로 변경하므로 DEBUG 동사를 IIS로 보낼 수 없게 됩니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  연결 대신 사용 하 여 수동 연결 (디버그 메뉴에서 선택 **프로세스에 연결**).  
  
     또는  
  
2.  변경 된 **IIS 웹 사이트 id** 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [웹 응용 프로그램 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



