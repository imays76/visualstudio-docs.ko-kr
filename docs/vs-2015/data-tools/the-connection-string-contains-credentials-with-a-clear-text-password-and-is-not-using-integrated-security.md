---
title: 일반 텍스트 암호를 사용 하 여 자격 증명을 포함 및 통합된 보안을 사용 하지 않는 연결 문자열 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f1ec13cab1b8c41225cb1934740b8dd3e7f59ac0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230877"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>연결 문자열에 일반 텍스트 암호가 있는 자격 증명이 포함되어 있으며 통합 보안을 사용하지 않습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
중요한 정보가 포함된 연결 문자열을 현재 DBML 파일 및 응용 프로그램 구성 파일에 저장하시겠습니까?  중요한 정보를 포함하지 않고 연결 문자열을 저장하려면 아니요를 클릭하세요.  
  
 연결 문자열에 포함된 암호와 같이 중요한 정보가 들어 있는 데이터 연결을 사용하는 경우 연결 문자열에 중요한 정보를 포함시키거나 제외시켜 프로젝트의 DBML 파일 및 응용 프로그램 구성 파일에 저장하는 옵션이 제공됩니다.  
  
> [!WARNING]
>  명시적으로 설정 합니다 **연결** 속성 **응용 프로그램 설정** 속성을 **False** DBML 파일에 암호가 추가 됩니다.  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>연결 문자열에 중요한 정보를 포함시켜 프로젝트의 응용 프로그램 설정에 저장하려면  
  
-   **예**를 클릭합니다.  
  
     연결 문자열이 응용 프로그램 설정대로 저장됩니다. 연결 문자열에는 중요한 정보가 일반 텍스트로 포함됩니다. DBML 파일에는 중요한 데이터가 포함되지 않습니다.  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>연결 문자열에 중요한 정보를 포함시키지 않고 프로젝트의 응용 프로그램 설정에 저장하려면  
  
-   **아니요**를 클릭합니다.  
  
     연결 문자열이 응용 프로그램 설정대로 저장되지만 암호는 포함되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)(Visual Studio의 LINQ to SQL 도구)

