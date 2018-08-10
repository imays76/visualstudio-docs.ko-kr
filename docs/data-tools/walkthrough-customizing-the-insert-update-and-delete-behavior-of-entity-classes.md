---
title: '연습: 사용자 지정 삽입, 업데이트 하 고 엔터티 클래스의 동작을 삭제'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 03ff1146-706e-4780-91cb-56a83df63eea
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: fb01ef51c0a44047e2caf2f23634ebe741cd2dcb
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174980"
---
# <a name="walkthrough-customize-the-insert-update-and-delete-behavior-of-entity-classes"></a>연습: 삽입, 업데이트 및 엔터티 클래스의 삭제 동작 사용자 지정

합니다 [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 만들고 LINQ to SQL 클래스 (엔터티 클래스)는 데이터베이스의 개체를 기반으로 하는 편집 하기 위한 시각적 디자인 화면을 제공 합니다. 사용 하 여 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index), SQL 데이터베이스에 액세스 하려면 LINQ 기술을 사용할 수 있습니다. 자세한 내용은 [LINQ (Language-integrated query)](/dotnet/csharp/linq/)합니다.

기본적으로 업데이트를 수행 하는 논리는 LINQ to SQL 런타임에서 제공 됩니다. 런타임이 기본 만듭니다 `Insert`, `Update`, 및 `Delete` (열 정 및 기본 키 정보) 테이블의 스키마를 기반으로 한 문입니다. 기본 동작을 사용 하지 않으려면 업데이트 동작을 구성할 수 있으며 필요한 삽입, 업데이트 및 데이터베이스의 데이터로 작업 하는 데 필요한 삭제를 수행 하기 위한 특정 저장된 프로시저를 지정할 수 있습니다. 엔터티 클래스가 뷰에 매핑되는 때와 같이 기본 동작이 생성되지 않은 경우에도 이렇게 할 수 있습니다. 또한 저장 프로시저를 통해 데이터베이스의 테이블에 액세스해야 하는 경우에 기본 업데이트 동작을 재정의할 수 있습니다. 자세한 내용은 [저장된 프로시저를 사용 하 여 작업을 사용자 지정](/dotnet/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures)합니다.

> [!NOTE]
> 이 연습에서는 가용성을 필요 합니다 **InsertCustomer**, **UpdateCustomer**, 및 **DeleteCustomer** Northwind 데이터베이스에 대해 저장 프로시저입니다.

이 연습에서는 저장 프로시저를 사용하여 데이터를 데이터베이스에 다시 저장하기 위한 기본 LINQ to SQL 런타임 동작을 재정의하는 단계에 대해 설명합니다.

이 연습에서는 다음 작업을 수행 하는 방법을 배웁니다.

-   새 Windows Forms 응용 프로그램을 만들고 LINQ to SQL 파일을 추가 합니다.

-   Northwind에 매핑되는 엔터티 클래스를 만들고 `Customers` 테이블입니다.

-   LINQ to SQL 참조 하는 개체 데이터 소스를 만들어 `Customer` 클래스입니다.

-   포함 하는 Windows Form을 만듭니다는 <xref:System.Windows.Forms.DataGridView> 에 바인딩되는 `Customer` 클래스.

-   폼의 저장 기능을 구현합니다.

-   만들 <xref:System.Data.Linq.DataContext> 저장 프로시저를 추가 하 여 메서드를 **O/R 디자이너**합니다.

-   구성 된 `Customer` 저장된 프로시저를 수행 하는 데 사용할 클래스를 삽입, 업데이트 및 삭제 합니다.

## <a name="prerequisites"></a>전제 조건

이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.

1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 합니다 **Visual Studio 설치 관리자**합니다. 에 **Visual Studio 설치 관리자**의 일부로 SQL Server Express LocalDB를 설치할 수 있습니다는 **데이터 저장 및 처리** 워크 로드 또는 개별 구성 요소로 합니다.

2.  다음이 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.

    1. Visual Studio에서 엽니다는 **SQL Server 개체 탐색기** 창입니다. (**SQL Server 개체 탐색기** 의 일부로 설치 된 **데이터 저장 및 처리** 에서 워크 로드를 **Visual Studio 설치 관리자**.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리**합니다.

       쿼리 편집기 창이 열립니다.

    2. 복사 합니다 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 클립보드에 있습니다. 이 T-SQL 스크립트부터에서 Northwind 데이터베이스를 만들고 데이터로 채웁니다.

    3. T-SQL 스크립트, 쿼리 편집기에 붙여넣고 선택한 합니다 **Execute** 단추입니다.

       짧은 시간 후 쿼리 실행이 완료 하 고 Northwind 데이터베이스 생성 됩니다.

## <a name="creating-an-application-and-adding-linq-to-sql-classes"></a>응용 프로그램 만들기 및 LINQ to SQL 클래스 추가

LINQ to SQL 클래스 작업 하 고 Windows Form에 데이터를 표시 하는 때문에 새 Windows Forms 응용 프로그램을 만들고 LINQ to SQL 클래스 파일을 추가 합니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-a-new-windows-forms-application-project-that-contains-linq-to-sql-classes"></a>LINQ to SQL 클래스에 포함 된 새 Windows Forms 응용 프로그램 프로젝트를 만들려면

1. Visual Studio에서에 **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.

2. 확장 **Visual C#** 하거나 **Visual Basic** 왼쪽 창에서 선택한 **Windows Desktop**합니다.

3. 가운데 창에서 선택 합니다 **Windows Forms 앱** 형식 프로젝션 합니다.

4. 프로젝트 이름을 **UpdatingWithSProcsWalkthrough**를 선택한 후 **확인**합니다.

     합니다 **UpdatingWithSProcsWalkthrough** 프로젝트에 추가한 만들어지면 **솔루션 탐색기**합니다.

4.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.

5.  클릭 합니다 **LINQ to SQL 클래스** 템플릿과 형식 **Northwind.dbml** 에 **이름** 상자.

6.  **추가**를 클릭합니다.

     빈 LINQ to SQL 클래스 파일 (**Northwind.dbml**) 프로젝트에 추가 되 고 **O/R 디자이너** 열립니다.

## <a name="create-the-customer-entity-class-and-object-data-source"></a>Customer 엔터티 클래스 및 개체 데이터 원본 만들기

LINQ to SQL 클래스 테이블을 끌어 데이터베이스 테이블에 매핑되는 만들기 **서버 탐색기** 하거나 **데이터베이스 탐색기** 에 **O/R 디자이너**합니다. 그러면 데이터베이스의 테이블에 매핑되는 LINQ to SQL 엔터티 클래스가 생성됩니다. 엔터티 클래스를 만든 후 이 클래스를 공용 속성이 있는 다른 클래스처럼 개체 데이터 소스로 사용할 수 있습니다.

### <a name="to-create-a-customer-entity-class-and-configure-a-data-source-with-it"></a>Customer 엔터티 클래스를 만들고 이 클래스를 사용하여 데이터 소스를 구성하려면

1.  **서버 탐색기** 또는 **데이터베이스 탐색기**를 찾습니다는 **고객** Northwind 샘플 데이터베이스의 SQL Server 버전에서 테이블입니다.

2.  끌어서 합니다 **고객** 노드에서 **서버 탐색기** 또는 **데이터베이스 탐색기** 에 **O/R 디자이너* 화면.

     라는 엔터티 클래스가 **고객** 만들어집니다. 이 클래스에는 Customers 테이블의 열에 해당하는 속성이 있습니다. 엔터티 클래스의 이름은 **고객** (없습니다 **고객**) Customers 테이블에서 단일 고객을 나타내므로 합니다.

    > [!NOTE]
    > 이러한 이름 바꾸기 동작 이라고 *복수화*합니다. 설정할 수 있습니다 또는 해제는 [옵션 대화 상자](../ide/reference/options-dialog-box-visual-studio.md)합니다. 자세한 내용은 [방법: 복수형 설정 및 해제 (O/R 디자이너)](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md)합니다.

3.  에 **빌드** 메뉴에서 클릭 **UpdatingwithSProcsWalkthrough 빌드** 프로젝트를 빌드합니다.

4.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.

5.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.

6.  클릭 **개체** 에 **데이터 소스 형식 선택** 페이지를 클릭 한 다음 **다음**합니다.

7.  확장 된 **UpdatingwithSProcsWalkthrough** 노드 찾아 선택 합니다 **고객** 클래스.

    > [!NOTE]
    > 경우는 **고객** 클래스를 사용할 수 없는 경우, 마법사를 취소, 프로젝트를 빌드 및 마법사를 다시 실행 합니다.
8.  클릭 **완료** 데이터 소스를 만들고 추가 하는 **고객** 엔터티 클래스를 **데이터 원본** 창입니다.

## <a name="create-a-datagridview-to-display-the-customer-data-on-a-windows-form"></a>Windows Form에 고객 데이터를 표시 하기 위해 DataGridView 만들기

LINQ에서 SQL 데이터 원본 항목을 끌어 엔터티 클래스에 바인딩되는 컨트롤을 만들 합니다 **데이터 원본** 창에서 Windows 폼입니다.

### <a name="to-add-controls-that-are-bound-to-the-entity-classes"></a>엔터티 클래스에 바인딩된 컨트롤을 추가하려면

1.  오픈 **Form1** 디자인 뷰에서 합니다.

2.  **데이터 원본** 창으로 끕니다 합니다 **고객** 노드 **Form1**합니다.

    > [!NOTE]
    > 표시할 합니다 **데이터 원본** 창에서 클릭 **데이터 소스 표시** 에 **데이터** 메뉴.

3.  오픈 **Form1** 코드 편집기에서.

4.  하지만 내 특정 메서드의 외부 폼에 전역 폼에 다음 코드를 추가 합니다 `Form1` 클래스:

    ```vb
    Private NorthwindDataContext1 As New NorthwindDataContext
    ```

    ```csharp
    private NorthwindDataContext northwindDataContext1
        = new NorthwindDataContext();
    ```

5.  `Form_Load` 이벤트에 대한 이벤트 처리기를 만들고 다음 코드를 처리기에 추가합니다.

    ```vb
    CustomerBindingSource.DataSource = NorthwindDataContext1.Customers
    ```

    ```csharp
    customerBindingSource.DataSource
        = northwindDataContext1.Customers;
    ```

## <a name="implement-save-functionality"></a>저장 기능을 구현

기본적으로 저장 단추를 사용할 수 없으며 저장 기능이 구현되지 않습니다. 또한 개체 데이터 소스에 대해 데이터 바인딩된 컨트롤을 만들 때 변경된 데이터를 데이터베이스에 저장하는 코드가 자동으로 추가되지 않습니다. 이 섹션에서는 저장을 사용 하도록 설정 하는 방법에 설명 단추 및 저장 기능을 구현 LINQ에 대 한 SQL 개체입니다.

### <a name="to-implement-save-functionality"></a>저장 기능을 구현하려면

1.  오픈 **Form1** 디자인 뷰에서 합니다.

2.  저장 선택 단추를 **CustomerBindingNavigator** (플로피 디스크 아이콘이 있는 단추).

3.  에 **속성** 창에서 설정 합니다 **사용** 속성을 **True**합니다.

4.  저장 단추를 두 번 클릭하여 이벤트 처리기를 만들고 코드 편집기로 전환합니다.

5.  저장 단추 이벤트 처리기에 다음 코드를 추가합니다.

    ```vb
    NorthwindDataContext1.SubmitChanges()
    ```

    ```csharp
    northwindDataContext1.SubmitChanges();
    ```

## <a name="override-the-default-behavior-for-performing-updates-inserts-updates-and-deletes"></a>업데이트 (삽입, 업데이트 및 삭제)를 수행 하는 것에 대 한 기본 동작 재정의

### <a name="to-override-the-default-update-behavior"></a>기본 업데이트 동작을 재정의하려면

1.  LINQ to SQL 파일에서 엽니다는 **O/R 디자이너**합니다. (두 번 클릭 합니다 **Northwind.dbml** 파일 **솔루션 탐색기**.)

2.  **서버 탐색기** 또는 **데이터베이스 탐색기**, Northwind 데이터베이스를 확장 **Stored Procedures** 노드를 찾습니다는 **InsertCustomers**하십시오 **UpdateCustomers**, 및 **DeleteCustomers** 저장 프로시저입니다.

3.  모든 3 개의 저장된 프로시저를 끌어 합니다 **O/R 디자이너**합니다.

     이러한 저장 프로시저가 메서드 창에 <xref:System.Data.Linq.DataContext> 메서드로 추가됩니다. 자세한 내용은 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.

4.  선택 된 **고객** 의 엔터티 클래스는 **O/R 디자이너**합니다.

5.  에 **속성** 창에서 합니다 **삽입** 속성입니다.

6.  줄임표 (**...** ) 옆에 **사용 하 여 런타임** 열려는 합니다 **동작 구성** 대화 상자.

7.  선택 **사용자 지정**합니다.

8.  선택 된 **InsertCustomers** 에서 메서드는 **사용자 지정** 목록입니다.

9. 클릭 **적용** 선택한 클래스 및 동작에 대 한 구성을 저장 합니다.

    > [!NOTE]
    > 계속을 클릭 하면으로 각 클래스/동작 조합에 대 한 동작을 구성할 수 있습니다 **적용** 각 변경 합니다. 클릭 하기 전에 클래스 또는 동작을 변경 하는 경우 **적용**, 경고 대화 상자가 표시 하는 모든 변경 내용을 적용할 수 있는 기회를 제공 합니다.

10. 선택 **업데이트** 에 **동작** 목록입니다.

11. 선택 **사용자 지정**합니다.

12. 선택 된 **UpdateCustomers** 에서 메서드는 **사용자 지정** 목록입니다.

     목록을 살펴보고 **메서드 인수** 하 고 **클래스 속성** 를 두 개의 **메서드 인수** 두 개의 **클래스 속성**테이블의 일부 열에 대 한 합니다. 이를 사용하면 손쉽게 변경 내용을 추적하고 동시성 위반을 확인하는 문을 만들 수 있습니다.

13. 지도 **Original_CustomerID** 메서드 인수를 합니다 **CustomerID (Original)** 클래스 속성입니다.

    > [!NOTE]
    > 기본적으로 메서드 인수는 이름이 일치하는 경우 클래스 속성에 매핑됩니다. 속성 이름이 변경 되거나 더 이상 테이블과 엔터티 클래스 간에 일치를 것이 있으면 경우 매핑할 해당 클래스 속성을 선택 합니다 **O/R 디자이너** 에서 올바른 매핑을 결정할 수 없습니다. 또한 메서드 인수를 매핑할 올바른 클래스 속성이 없는 경우 설정할 수 있습니다 합니다 **클래스 속성** 값을 **(없음)** 합니다.

14. 클릭 **적용** 선택한 클래스 및 동작에 대 한 구성을 저장 합니다.

15. 선택 **삭제할** 에 **동작** 목록입니다.

16. 선택 **사용자 지정**합니다.

17. 선택 된 **DeleteCustomers** 에서 메서드는 **사용자 지정** 목록입니다.

18. 지도 **Original_CustomerID** 메서드 인수를 합니다 **CustomerID (Original)** 클래스 속성입니다.

19. **확인**을 클릭합니다.

> [!NOTE]
> LINQ to SQL 삽입 하는 동안 identity (자동 증분), rowguidcol (데이터베이스에서 생성 된 GUID) 및 timestamp 열에 대해 자동으로 데이터베이스에서 생성 된 값을 처리 하는 주목할 만한 것은이 연습에서는 문제가 없지만 및 업데이트합니다. 데이터베이스에서 생성된 값이 다른 형식의 열에 있으면 null 값이라는 예기치 않은 결과가 발생합니다. 데이터베이스에서 생성 된 값을 반환 하려면 직접 설정 해야 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 를 `true` 하 고 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> 중 하나를: [AutoSync.Always](<xref:System.Data.Linq.Mapping.AutoSync.Always>)를 [AutoSync.OnInsert](<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>), 또는 [AutoSync.OnUpdate](<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate>)합니다.

## <a name="test-the-application"></a>응용 프로그램 테스트

다시 확인 하려면 응용 프로그램을 실행 합니다 **UpdateCustomers** 저장된 프로시저가 데이터베이스에서 고객 레코드를 올바르게 업데이트 합니다.

1.  **F5**키를 누릅니다.

2.  업데이트 동작을 테스트 하려면 그리드에서 레코드를 수정 합니다.

3.  Insert 동작을 테스트 하려면 새 레코드를 추가 합니다.

4.  저장 단추를 클릭하여 변경 내용을 데이터베이스에 다시 저장합니다.

5.  폼을 닫아 디버깅을

6.  키를 눌러 **F5** 하 고 업데이트 된 레코드와 새로 삽입된 된 레코드 유지 함을 확인 합니다.

7.  만든 새 레코드를 삭제는 delete 동작을 테스트 하려면 3 단계.

8.  저장을 클릭 합니다. 변경 내용을 전송 하 고 데이터베이스에서 삭제 된 레코드를 제거 하는 단추입니다.

9. 폼을 닫아 디버깅을

10. 키를 눌러 **F5** 데이터베이스에서 삭제 된 레코드가 제거 되었는지 확인 합니다.

    > [!NOTE]
    > 응용 프로그램에서 값에 따라 SQL Server Express Edition을 사용 하는 경우는 **출력 디렉터리로 복사** 데이터베이스 파일의 속성 변경 내용을 나타나지 않을 수 있습니다를 누르면 **F5** 10 단계에서 합니다.

## <a name="next-steps"></a>다음 단계

응용 프로그램 요구 사항에 따라 LINQ to SQL 엔터티 클래스 만들기 후 수행 하는 것이 좋습니다는 여러 단계가 있습니다. 이 응용 프로그램에서 개선할 수 있는 몇 가지 사항은 다음과 같습니다.

- 업데이트 동안 동시성 검사를 구현합니다. 정보를 참조 하세요 [낙관적 동시성: 개요](/dotnet/framework/data/adonet/sql/linq/optimistic-concurrency-overview)합니다.

- LINQ 쿼리를 추가하여 데이터를 필터링합니다. 정보를 참조 하세요 [LINQ 쿼리 (C#) 소개](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [DataContext 메서드](../data-tools/datacontext-methods-o-r-designer.md)
- [방법: 업데이트, 삽입 및 삭제 하는 데 저장된 프로시저를 할당 합니다.](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [LINQ to SQL 쿼리](/dotnet/framework/data/adonet/sql/linq/linq-to-sql-queries)