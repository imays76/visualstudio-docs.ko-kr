---
title: '연습: 저장 프로시저는 Northwind Customers 테이블에 대 한 업데이트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- Northwind sample database
- stored procedures [Visual Studio]
- O/R Designer, stored procedures
ms.assetid: 6fd9e7e0-6862-44d3-9710-acc5a72d4ffd
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 4972c1341490f78bba03bdd390ac13903c55be84
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49204050"
---
# <a name="walkthrough-creating-update-stored-procedures-for-the-northwind-customers-table"></a>연습: Northwind Customers 테이블의 업데이트 저장 프로시저 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

일부 도움말 항목에는 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] 설명서 Customers 테이블의 데이터 업데이트 (삽입, 업데이트 및 삭제)를 수행 하는 것에 대 한 Northwind 샘플 데이터베이스의 저장된 프로시저를 추가 해야 합니다.  
  
 이 연습에서는 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]용 Northwind 샘플 데이터베이스에서 이러한 추가 저장 프로시저를 만드는 지침을 제공합니다.  
  
 이 항목 뒷부분의 다음 단계 섹션에서는 이러한 추가 저장 프로시저를 사용하는 방법을 보여주는 항목에 대한 링크를 제공합니다.  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   Northwind 샘플 데이터베이스에 대한 데이터 연결 만들기  
  
-   저장 프로시저 만들기  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스의 SQL Server 버전 액세스 권한. 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
## <a name="connecting-to-the-northwind-database"></a>Northwind 데이터베이스에 연결  
 이 연습에서는 Northwind 데이터베이스의 SQL Server 버전에 연결해야 합니다. 다음 절차에서는 데이터 연결을 만드는 지침을 제공합니다.  
  
> [!NOTE]
>  Northwind 데이터베이스에 대한 데이터 연결이 이미 있는 경우 다음 섹션인 저장 프로시저 만들기로 이동하면 됩니다.  
  
#### <a name="to-create-a-data-connection-to-the-northwind-sql-server-database"></a>Northwind SQL Server 데이터베이스에 대한 데이터 연결을 만들려면  
  
1.  에 **뷰** 메뉴에서 클릭 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
2.  마우스 오른쪽 단추로 클릭 **데이터 연결** 누릅니다 **연결 추가**합니다.  
  
3.  에 **데이터 소스 선택** 대화 상자, 클릭 **Microsoft SQL Server**를 클릭 하 고 **확인**합니다.  
  
     경우는 **연결 추가** 대화 상자가 열리고 및 **데이터 원본** 아닙니다 **Microsoft SQL Server (SqlClient)**, 클릭 **변경** 열려는 **데이터 소스 선택/변경** 대화 상자, 클릭 **Microsoft SQL Server**를 클릭 하 고 **확인**합니다.  
  
4.  클릭 된 **서버 이름** 드롭다운 목록에서 나열 하거나 Northwind 데이터베이스가 있는 서버의 이름을 입력 합니다.  
  
5.  클릭 하거나 데이터베이스 또는 응용 프로그램의 요구 사항에 따라 **Windows 인증 사용** 하거나 특정 사용자 이름 및 암호를 사용 하 여 SQL Server를 실행 하는 컴퓨터에 로그온 할 (**SQLServer인증**).  
  
6.  Northwind 데이터베이스를 클릭 합니다 **데이터베이스 이름 선택 또는 입력** 목록입니다.  
  
7.  **확인**을 클릭합니다.  
  
     데이터 연결을 추가할 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
## <a name="creating-the-stored-procedures"></a>저장 프로시저 만들기  
 저장된 프로시저를 사용 하 여 Northwind 데이터베이스에 대해 제공된 된 SQL 스크립트를 실행 하 여 만들기는 [Visual Database Tools](http://msdn.microsoft.com/en-us/6b145922-2f00-47db-befc-bf351b4809a1) 에서 사용할 수 있습니다 **서버 탐색기** /  **데이터베이스 탐색기**합니다.  
  
#### <a name="to-create-the-stored-procedures-by-using-a-sql-script"></a>SQL 스크립트를 사용하여 저장 프로시저를 만들려면  
  
1.  Northwind 데이터베이스에 확장 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
2.  마우스 오른쪽 단추로 클릭 합니다 **저장 프로시저** 노드와 클릭 **새 저장 프로시저 추가**합니다.  
  
3.  다음 코드를 코드 편집기에 붙여 넣습니다. 이때 `CREATE PROCEDURE` 템플릿을 다음과 같이 바꿉니다.  
  
    ```  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'SelectCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.[SelectCustomers]  
    GO  
  
    CREATE PROCEDURE dbo.[SelectCustomers]  
    AS  
        SET NOCOUNT ON;  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM dbo.Customers  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'InsertCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.InsertCustomers  
    GO  
  
    CREATE PROCEDURE dbo.InsertCustomers  
    (  
        @CustomerID nchar(5),  
        @CompanyName nvarchar(40),  
        @ContactName nvarchar(30),  
        @ContactTitle nvarchar(30),  
        @Address nvarchar(60),  
        @City nvarchar(15),  
        @Region nvarchar(15),  
        @PostalCode nvarchar(10),  
        @Country nvarchar(15),  
        @Phone nvarchar(24),  
        @Fax nvarchar(24)  
    )  
    AS  
        SET NOCOUNT OFF;  
    INSERT INTO [dbo].[Customers] ([CustomerID], [CompanyName], [ContactName], [ContactTitle], [Address], [City], [Region], [PostalCode], [Country], [Phone], [Fax]) VALUES (@CustomerID, @CompanyName, @ContactName, @ContactTitle, @Address, @City, @Region, @PostalCode, @Country, @Phone, @Fax);  
  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE (CustomerID = @CustomerID)  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'UpdateCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.UpdateCustomers  
    GO  
  
    CREATE PROCEDURE dbo.UpdateCustomers  
    (  
        @CustomerID nchar(5),  
        @CompanyName nvarchar(40),  
        @ContactName nvarchar(30),  
        @ContactTitle nvarchar(30),  
        @Address nvarchar(60),  
        @City nvarchar(15),  
        @Region nvarchar(15),  
        @PostalCode nvarchar(10),  
        @Country nvarchar(15),  
        @Phone nvarchar(24),  
        @Fax nvarchar(24),  
        @Original_CustomerID nchar(5)  
    )  
    AS  
        SET NOCOUNT OFF;  
    UPDATE [dbo].[Customers] SET [CustomerID] = @CustomerID, [CompanyName] = @CompanyName, [ContactName] = @ContactName, [ContactTitle] = @ContactTitle, [Address] = @Address, [City] = @City, [Region] = @Region, [PostalCode] = @PostalCode, [Country] = @Country, [Phone] = @Phone, [Fax] = @Fax WHERE (([CustomerID] = @Original_CustomerID));  
  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE (CustomerID = @CustomerID)  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'DeleteCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.DeleteCustomers  
    GO  
  
    CREATE PROCEDURE dbo.DeleteCustomers  
    (  
        @Original_CustomerID nchar(5)  
    )  
    AS  
        SET NOCOUNT OFF;  
    DELETE FROM [dbo].[Customers] WHERE (([CustomerID] = @Original_CustomerID))  
    GO  
    ```  
  
4.  코드 편집기에서 모든 텍스트를 선택 하 고, 선택한 텍스트를 마우스 오른쪽 단추로 클릭, 클릭 **선택 항목 실행**합니다.  
  
     Northwind 데이터베이스에 대해 SelectCustomers, InsertCustomers, UpdateCustomers 및 DeleteCustomers 저장 프로시저가 만들어집니다.  
  
## <a name="next-steps"></a>다음 단계  
 저장 프로시저를 만든 후에는 해당 저장 프로시저를 사용하는 방법을 보여주는 다음 연습을 진행해 보세요.  
  
 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
  
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)  
  
 [연습: 엔터티 클래스의 삽입, 업데이트 및 삭제 동작을 사용자 지정](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)