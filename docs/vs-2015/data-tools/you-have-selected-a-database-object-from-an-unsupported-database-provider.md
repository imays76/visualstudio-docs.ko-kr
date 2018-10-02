---
title: 데이터베이스 개체에서 지원 되지 않는 데이터베이스 공급자를 선택한 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2c225e00a6d303bff16e30fabd2f3e8e0e9d40ca
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556648"
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>지원되지 않는 데이터베이스 공급자에서 데이터베이스 공급자를 선택했습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Visual Studio 2017 설명서](https://docs.microsoft.com/en-us/visualstudio/)합니다.  
  
합니다 [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)])에.NET Framework Data Provider for SQL Server 지원 (<xref:System.Data.SqlClient>). 클릭할 수 있지만 **확인** 하며 지원 되지 않는 데이터베이스 공급자의에서 개체를 사용 하려면 계속 하기, 런타임 시 예기치 않은 동작이 발생할 수 있습니다.  
  
> [!NOTE]
>  .NET Framework Data Provider for SQL Server를 사용하는 데이터 연결만 지원됩니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   클릭 **확인** 를 계속 해 서 지원 되지 않는 데이터베이스 공급자를 사용 하는 연결에 매핑되는 엔터티 클래스를 디자인 합니다. 지원되지 않는 데이터베이스 공급자를 사용하면 예상치 못한 동작이 발생할 수도 있습니다.  
  
     또는  
  
-   클릭 **취소**합니다.  
  
     작업이 중지됩니다. .NET Framework Provider for SQL Server를 사용하는 데이터 연결을 만들거나 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [.NET framework 데이터 공급자](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)

