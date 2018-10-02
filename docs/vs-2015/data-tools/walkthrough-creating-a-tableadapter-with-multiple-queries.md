---
title: '연습: 여러 개의 쿼리가 있는 TableAdapter 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
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
- TableAdapter queries, creating
- data [Visual Studio], TableAdapters
- TableAdapters, creating
- data [Visual Studio], walkthroughs
- queries [Visual Studio], TableAdapters
ms.assetid: f784dc4d-d514-4ade-8226-f8271c5b1ed8
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: e48750cf876f561b25802fd20b1e270215a1b605
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553040"
---
# <a name="walkthrough-creating-a-tableadapter-with-multiple-queries"></a>연습: 여러 개의 쿼리가 있는 TableAdapter 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서 사용 하 여 데이터 집합에서 TableAdapter를 만듭니다는 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)합니다. 연습에서 두 번째 쿼리를 만드는 과정을 단계별로 안내 합니다 [TableAdapter](../data-tools/tableadapter-overview.md) 를 사용 하 여는 [Tableadapter 편집](../data-tools/editing-tableadapters.md) 내에서 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md)합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새로 만들 **Windows 응용 프로그램** 프로젝트입니다.  
  
-   만들기 및 사용 하 여 데이터 집합을 작성 하 여 응용 프로그램에서 데이터 원본을 구성 합니다 **데이터 소스 구성 마법사**합니다.  
  
-   새 데이터 집합을 열어 합니다 **데이터 집합 디자이너**합니다.  
  
-   사용 하 여 TableAdapter에 쿼리를 추가 합니다 **TableAdapter 쿼리 구성 마법사**합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스(SQL Server 또는 Access 버전) 액세스 권한. 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
## <a name="creating-a-new-windows-application"></a>새 Windows 응용 프로그램 만들기  
 첫 번째 단계에서는 Windows 응용 프로그램을 만듭니다.  
  
#### <a name="to-create-a-new-windows-application-project"></a>새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로그래밍 언어를 선택 합니다 **프로젝트 형식** 창입니다.  
  
3.  클릭 **Windows 응용 프로그램** 에 **템플릿** 창입니다.  
  
4.  프로젝트 이름을 `TableAdapterQueriesWalkthrough`를 클릭 하 고 **확인**합니다.  
  
     Visual Studio 프로젝트를 추가 합니다 **솔루션 탐색기** 디자이너에서 새 폼이 표시 됩니다.  
  
## <a name="creating-a-database-data-source-with-a-tableadapter"></a>TableAdapter가 포함된 데이터베이스 데이터 소스 만들기  
 이 단계에서는 사용 하 여 데이터 소스를 만듭니다는 **데이터 소스 구성 마법사** 기반을 `Customers` Northwind 샘플 데이터베이스의 테이블입니다. 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다. Northwind 샘플 데이터베이스 설정에 대 한 내용은 참조 하세요 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스** 를 선택하고 **다음**을 클릭합니다.  
  
4.  에 **데이터 연결 선택** 페이지 중 하나를 수행 합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자.  
  
5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 클릭 옵션을 선택 **다음**합니다.  
  
6.  클릭 **다음** 에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지입니다.  
  
7.  확장 된 **테이블** 노드에서 **데이터베이스 개체 선택** 페이지입니다.  
  
8.  선택 된 **고객** 테이블을 마우스 클릭 **마침**합니다.  
  
     합니다 **NorthwindDataSet** 프로젝트에 추가 됩니다 및 **고객** 테이블에 표시 됩니다는 **데이터 원본** 창입니다.  
  
## <a name="opening-the-dataset-in-the-dataset-designer"></a>데이터 집합 디자이너에서 데이터 집합 열기  
  
#### <a name="to-open-the-dataset-in-the-dataset-designer"></a>데이터 집합 디자이너에서 데이터 집합을 열려면  
  
1.  마우스 오른쪽 단추로 클릭 **NorthwindDataset** 에 **데이터 원본** 창입니다.  
  
2.  바로 가기 메뉴에서 선택 **디자이너를 사용 하 여 데이터 집합 편집**합니다.  
  
     NorthwindDataset 열립니다는 **데이터 집합 디자이너**합니다.  
  
## <a name="adding-a-second-query-to-the-customerstableadapter"></a>CustomersTableAdapter에 두 번째 쿼리 추가  
 마법사 생성 데이터 집합은는 **고객이** 데이터 테이블 및 **CustomersTableAdapter**합니다. 연습의이 섹션에서는 두 번째 쿼리를 추가 합니다 **CustomersTableAdapter**합니다.  
  
#### <a name="to-add-a-query-to-the-customerstableadapter"></a>CustomersTableAdapter에 쿼리를 추가하려면  
  
1.  끌어서를 **쿼리** 에서 **데이터 집합** 탭의 **도구 상자** 에 **고객** 테이블.  
  
     합니다 [Tableadapter 편집](../data-tools/editing-tableadapters.md) 열립니다.  
  
2.  선택 **사용 하 여 SQL 문을**를 클릭 하 고 **다음**합니다.  
  
3.  선택 **행을 반환 하는 SELECT**를 클릭 하 고 **다음**합니다.  
  
4.  다음과 같이 WHERE 절을 쿼리에 추가합니다.  
  
    ```  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax   
    FROM Customers   
    WHERE City = @City  
    ```  
  
    > [!NOTE]
    >  Access 버전의 Northwind 사용 하는 경우 대체는 @City 물음표를 사용 하 여 매개 변수입니다. (`SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE City = ?`)  
  
5.  에 **생성할 메서드 선택** 페이지에서 이름을 합니다 **DataTable 채우기** 메서드 `FillByCity`합니다.  
  
    > [!NOTE]
    >  메서드를 **DataTable 반환** 확인란의 선택을 취소 하거나 기본 이름을 그대로 수 있도록이 연습에서는 사용 되지 않습니다.  
  
6.  클릭 **다음** 마법사를 완료 합니다.  
  
     합니다 **FillByCity** 쿼리가 추가 됩니다 합니다 **CustomersTableAdapter**합니다.  
  
## <a name="adding-code-to-execute-the-additional-query-on-the-form"></a>폼에서 추가 쿼리를 실행하는 코드 추가  
  
#### <a name="to-execute-the-query"></a>쿼리를 실행하려면  
  
1.  선택 **Form1** 에 **솔루션 탐색기**를 클릭 하 고 **뷰 디자이너**합니다.  
  
2.  끌어서 합니다 **고객** 에서 노드를 **데이터 원본** 창을 **Form1**합니다.  
  
3.  선택 하 여 코드 보기를 변경할 **코드** 에서 합니다 **보기** 메뉴.  
  
4.  `Form1_Load` 이벤트 처리기의 코드를 다음 코드로 바꿔 `FillByCity` 쿼리를 실행합니다.  
  
     [!code-csharp[VbRaddataTableAdapters#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Form1.cs#1)]
     [!code-vb[VbRaddataTableAdapters#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Form1.vb#1)]  
  
## <a name="running-the-application"></a>응용 프로그램 실행  
  
#### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면  
  
-   F5 키를 누릅니다.  
  
-   `City` 값이 `Seattle`인 고객으로 표가 채워집니다.  
  
## <a name="next-steps"></a>다음 단계  
  
### <a name="to-add-functionality-to-your-application"></a>응용 프로그램에 기능을 추가하려면  
  
-   <xref:System.Windows.Forms.TextBox> 컨트롤과 <xref:System.Windows.Forms.Button> 컨트롤을 추가하고 텍스트 상자의 값을 쿼리로 전달합니다. (`CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, TextBox1.Text)`).  
  
-   데이터 집합에 있는 데이터 테이블의 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트에 유효성 검사 논리를 추가합니다. 자세한 내용은 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [Tableadapter 만들기 및 구성](../data-tools/create-and-configure-tableadapters.md)   
 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)   
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)