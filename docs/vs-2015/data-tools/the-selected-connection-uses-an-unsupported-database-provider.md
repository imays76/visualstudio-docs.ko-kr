---
title: 선택한 연결에 지원 되지 않는 데이터베이스 공급자를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4e38bda495521bf81c6eb4b9a00a0f32620a71fb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542783"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>선택한 연결에서 지원되지 않는 데이터베이스 공급자를 사용합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [선택한 연결에 지원 되지 않는 데이터베이스 공급자를 사용 하 여](https://docs.microsoft.com/visualstudio/data-tools/the-selected-connection-uses-an-unsupported-database-provider)입니다.  
  
  
이 메시지는.NET Framework Data Provider for SQL Server에서 사용 하지 않는 항목을 끌어 오면 나타납니다 **서버 탐색기**/**데이터베이스 탐색기** 에 [LINQ to SQL Visual Studio의 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)합니다.  
  
 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]에서는 .NET Framework Provider for SQL Server를 사용하는 데이터 연결만 지원합니다. Microsoft SQL Server 또는 Microsoft SQL Server 데이터베이스 파일에 대한 연결만 유효합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   .NET Framework Data Provider for SQL Server를 사용하는 데이터 연결의 항목만 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]에 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.SqlClient>   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [.NET framework 데이터 공급자](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [데이터 응용 프로그램 만들기](../data-tools/creating-data-applications.md)

