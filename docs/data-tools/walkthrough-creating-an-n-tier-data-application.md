---
title: '연습: N 계층 데이터 응용 프로그램 만들기'
ms.date: 09/08/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, creating
- n-tier applications, walkthroughs
ms.assetid: d15e4d31-2839-48d9-9e0e-2e73404d82a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 87b88c6fc8c6add2c93721b46165ffd295f4d614
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942896"
---
# <a name="walkthrough-create-an-n-tier-data-application"></a>연습: n 계층 데이터 응용 프로그램 만들기
*N 계층* 데이터 응용 프로그램은 여러 논리 계층으로 분리 되어 데이터에 액세스 하는 응용 프로그램 또는 *계층*합니다. 응용 프로그램 구성 요소를 개별 계층으로 분리하면 응용 프로그램의 확장성과 유지 관리 가능성이 높아집니다. 이는 전체 솔루션을 다시 설계하지 않고도 단일 계층에 적용할 수 있는 새로운 기술을 보다 쉽게 도입할 수 있기 때문입니다. N 계층 아키텍처에는 표시 계층, 중간 계층 및 데이터 계층이 포함됩니다. 중간 계층에는 대개 데이터 액세스 계층, 비즈니스 논리 계층 및 인증, 유효성 검사 등의 공유 구성 요소가 포함됩니다. 데이터 계층에는 관계형 데이터베이스가 포함됩니다. 표시 계층에 액세스하는 최종 사용자로부터 격리된 상태를 유지하기 위해 N 계층 응용 프로그램에서는 보통 중요한 정보가 중간 계층의 데이터 액세스 계층에 저장됩니다. 자세한 내용은 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)합니다.

N 계층 응용 프로그램의 여러 계층을 분리하는 방법 중 하나는 응용 프로그램에 포함할 각 계층에 대해 개별 프로젝트를 만드는 것입니다. 형식화된 데이터 집합에는 생성된 데이터 집합 및 `DataSet Project` 코드를 포함해야 하는 프로젝트를 결정하는 `TableAdapter` 속성이 포함됩니다.

이 연습에서는 데이터 집합을 구분 하는 방법에 설명 하 고 `TableAdapter` 코드를 사용 하 여 개별 클래스 라이브러리 프로젝트로 **데이터 집합 디자이너**합니다. 만든 데이터 집합 및 TableAdapter 코드를 분리 한 후에 [Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) 데이터 액세스 계층을 호출 하는 서비스입니다. 마지막으로, 프레젠테이션 계층으로 Windows Forms 응용 프로그램을 만듭니다. 이 계층은 데이터 서비스에서 데이터에 액세스합니다.

이 연습에서는 다음 단계를 수행 합니다.

-   여러 프로젝트가 포함 된 새 n 계층 솔루션을 만듭니다.

-   N 계층 솔루션에 클래스 라이브러리 프로젝트 두 개를 추가합니다.

-   사용 하 여 형식화 된 데이터 집합을 만들 합니다 **데이터 소스 구성 마법사**합니다.

-   생성 된 구분 [Tableadapter](create-and-configure-tableadapters.md) 및 데이터 집합 코드를 별도 프로젝트로 합니다.

-   데이터 액세스 계층으로 호출할 WCF(Windows Communication Foundation) 서비스를 만듭니다.

-   데이터 액세스 계층에서 데이터를 검색하기 위한 함수를 서비스에서 만듭니다.

-   표시 계층으로 사용할 Windows Forms 응용 프로그램을 만듭니다.

-   데이터 소스에 바인딩되는 Windows Forms 컨트롤을 만듭니다.

-   데이터 테이블을 채우는 코드를 작성합니다.

![비디오 링크](../data-tools/media/playvideo.gif) 이 항목의 비디오 버전을 참조 하세요. [Video How to: n 계층 데이터 응용 프로그램을 만드는](http://go.microsoft.com/fwlink/?LinkId=115188)합니다.

## <a name="prerequisites"></a>전제 조건
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.

1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 합니다 **Visual Studio 설치 관리자**합니다. 에 **Visual Studio 설치 관리자**의 일부로 SQL Server Express LocalDB를 설치할 수 있습니다는 **.NET 데스크톱 개발** 워크 로드 또는 개별 구성 요소로 합니다.

2.  다음이 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.

    1. Visual Studio에서 엽니다는 **SQL Server 개체 탐색기** 창입니다. (**SQL Server 개체 탐색기** 의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리**합니다.

       쿼리 편집기 창이 열립니다.

    2. 복사 합니다 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 클립보드에 있습니다. 이 T-SQL 스크립트부터에서 Northwind 데이터베이스를 만들고 데이터로 채웁니다.

    3. T-SQL 스크립트, 쿼리 편집기에 붙여넣고 선택한 합니다 **Execute** 단추입니다.

       짧은 시간 후 쿼리 실행이 완료 하 고 Northwind 데이터베이스 생성 됩니다.

## <a name="create-the-n-tier-solution-and-class-library-to-hold-the-dataset-dataentitytier"></a>N 계층 솔루션 및 클래스 라이브러리 (DataEntityTier) 데이터 집합을 보관 만들기
 이 연습의 첫 단계에서는 솔루션과 클래스 라이브러리 프로젝트 두 개를 만듭니다. 데이터 집합을 보유 하는 첫 번째 클래스 라이브러리 (생성 된 형식의 `DataSet` 클래스 및 응용 프로그램의 데이터를 보유 하는 Datatable)입니다. 이 프로젝트는 응용 프로그램의 데이터 엔터티 계층으로 사용되며 대개 중간 계층에 배치됩니다. 데이터 집합을 초기 데이터 집합을 만들면 하 고 자동으로 두 클래스 라이브러리로 코드를 구분 합니다.

> [!NOTE]
> 클릭 하기 전에 프로젝트 및 솔루션의 올바르게 이름은 **확인**합니다. 그러면 이 연습을 보다 쉽게 완료할 수 있습니다.

### <a name="to-create-the-n-tier-solution-and-dataentitytier-class-library"></a>N 계층 솔루션 및 DataEntityTier 클래스 라이브러리를 만들려면

1. Visual Studio에서에 **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.

2. 확장 **Visual C#** 하거나 **Visual Basic** 왼쪽 창에서 선택한 **Windows Desktop**합니다.

3. 가운데 창에서 선택 합니다 **클래스 라이브러리** 형식 프로젝션 합니다.

4. 프로젝트 이름을 **DataEntityTier**합니다.

5. 솔루션의 이름을 **NTierWalkthrough**를 선택한 후 **확인**합니다.

     DataEntityTier 프로젝트가 포함 된 NTierWalkthrough 솔루션이 만들어지고 추가할 **솔루션 탐색기**합니다.

## <a name="create-the-class-library-to-hold-the-tableadapters-dataaccesstier"></a>TableAdapters (DataAccessTier)를 포함할 클래스 라이브러리를 만들려면
 DataEntityTier 프로젝트를 만든 후 다음 단계에서는 다른 클래스 라이브러리 프로젝트를 만듭니다. 이 프로젝트는 생성 된 Tableadapter를 보유 하 고 호출 되는 *데이터 액세스 계층* 응용 프로그램입니다. 데이터 액세스 계층은 데이터베이스에 연결하는 데 필요한 정보를 포함하며 대개 중간 계층에 배치됩니다.

### <a name="to-create-a-separate-class-library-for-the-tableadapters"></a>Tableadapter에 대 한 별도 클래스 라이브러리를 만들려면

1.  솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** > **새 프로젝트**합니다.

2.  에 **새 프로젝트** 대화 상자의 선택 가운데 창에서 **클래스 라이브러리**합니다.

3.  프로젝트 이름을 **DataAccessTier** 선택한 **확인**합니다.

     DataAccessTier 프로젝트가 만들어져 NTierWalkthrough 솔루션에 추가됩니다.

## <a name="create-the-dataset"></a>데이터 집합을 만들려면
 다음 단계에서는 형식화된 데이터 집합을 만듭니다. Dataset 클래스를 사용 하 여 형식화 된 데이터 집합을 만듭니다 (포함 `DataTables` 클래스) 및 `TableAdapter` 단일 프로젝트에서 클래스입니다. 모든 클래스는 단일 파일로 생성됩니다. Dataset 클래스는 그대로 두고, 다른 프로젝트를 이동 하는 것이 데이터 집합 및 Tableadapter를 다른 프로젝트로 분리 하면는 `TableAdapter` 원래 프로젝트에서 클래스입니다. 따라서 궁극적으로 Tableadapter (DataAccessTier 프로젝트) 포함 하는 프로젝트에서 데이터 집합을 만듭니다. 사용 하 여 데이터 집합을 만들려면 합니다 **데이터 소스 구성 마법사**합니다.

> [!NOTE]
> 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다. Northwind 샘플 데이터베이스를 설정 하는 방법에 대 한 정보를 참조 하세요 [방법: 샘플 데이터베이스 설치](../data-tools/installing-database-systems-tools-and-samples.md)합니다.

### <a name="to-create-the-dataset"></a>데이터 집합을 만들려면

1.  선택 된 **DataAccessTier** 에 **솔루션 탐색기**합니다.

2.  에 **데이터** 메뉴에서 **데이터 소스 표시**합니다.

3.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.

4.  에 **데이터 소스 형식 선택** 페이지에서 **데이터베이스** 선택한 후 **다음**합니다.

5.  에 **데이터 연결 선택** 페이지에서 다음 작업 중 하나를 수행 합니다.

     Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.

     또는

     선택 **새 연결** 열려는 합니다 **연결 추가** 대화 상자.

6.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 하 여 선택한 옵션을 선택 **다음**합니다.

    > [!NOTE]
    > SQL Server에 연결하는 대신 로컬 데이터베이스 파일을 선택한 경우 프로젝트에 파일을 추가할지를 묻는 메시지가 표시될 수 있습니다. 선택할 **예** 데이터베이스 파일을 프로젝트에 추가 합니다.

7.  선택 **다음** 에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지입니다.

8.  **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.

9.  에 대 한 확인란을 선택 합니다 **고객** 및 **주문** 테이블을 선택한 후 **마침**합니다.

     NorthwindDataSet DataAccessTier 프로젝트에 추가 되 고에 표시 되는 **데이터 원본** 창입니다.

## <a name="separate-the-tableadapters-from-the-dataset"></a>데이터 집합에서 TableAdapters를 분리 합니다.
 데이터 집합을 만든 후에는 생성된 데이터 집합 클래스를 TableAdapters에서 분리합니다. 설정 하 여이 작업을 수행 합니다 **데이터 집합 프로젝트** 속성을 프로젝트의 클래스를 저장할 분리 된 데이터 집합의 이름입니다.

### <a name="to-separate-the-tableadapters-from-the-dataset"></a>데이터 집합에서 TableAdapters를 분리하려면

1. 두 번 클릭 **NorthwindDataSet.xsd** 에 **솔루션 탐색기** 에서 데이터 집합을 여는 **데이터 집합 디자이너**합니다.

2. 디자이너의 빈 영역을 선택 합니다.

3. 찾을 합니다 **데이터 집합 프로젝트** 에서 노드를 **속성** 창입니다.

4. 에 **데이터 집합 프로젝트** 목록에서 **DataEntityTier**합니다.

5. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.

   데이터 집합 및 TableAdapters가 두 클래스 라이브러리 프로젝트로 분리됩니다. 원래 전체 데이터 집합을 포함 하는 프로젝트 (`DataAccessTier`) 이제는 TableAdapters만 포함 되어 있습니다. 에 지정 된 프로젝트를 **데이터 집합 프로젝트** 속성 (`DataEntityTier`) 형식화 된 데이터 집합을 포함 합니다. *집합인 NorthwindDataSet.Dataset.Designer.vb* (또는  *NorthwindDataSet.Dataset.Designer.cs*).

> [!NOTE]
> 데이터 집합 및 TableAdapters를 분리할 때는 (설정 하 여 합니다 **데이터 집합 프로젝트** 속성), 프로젝트의 기존 부분 데이터 집합 클래스가 자동으로 이동 되지 것입니다. 따라서 데이터 집합 프로젝트로 기존 데이터 집합 부분 클래스를 수동으로 이동해야 합니다.

## <a name="create-a-new-service-application"></a>새 서비스 응용 프로그램 만들기
이 연습에는 WCF 서비스를 사용 하 여 데이터 액세스 계층에 액세스 하려면 새 WCF 서비스 응용 프로그램을 만들어 보겠습니다 방법을 보여 줍니다.

### <a name="to-create-a-new-wcf-service-application"></a>새 WCF 서비스 응용 프로그램을 만들려면

1.  솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** > **새 프로젝트**합니다.

2.  에 **새 프로젝트** 대화 상자의 왼쪽 창에서 선택한 **WCF**합니다.  가운데 창에서 선택 **WCF 서비스 라이브러리**합니다.

3.  프로젝트 이름을 **DataService** 선택한 **확인**합니다.

     DataService 프로젝트가 만들어져 NTierWalkthrough 솔루션에 추가됩니다.

## <a name="create-methods-in-the-data-access-tier-to-return-the-customers-and-orders-data"></a>Customers 및 orders 데이터를 반환 하는 데이터 액세스 계층에서 메서드를 만듭니다.
 데이터 서비스에서 데이터 액세스 계층의 두 메서드를 호출 해야 합니다. `GetCustomers` 및 `GetOrders`합니다. 이러한 메서드는 Northwind 반환 `Customers` 고 `Orders` 테이블입니다. 만들기는 `GetCustomers` 하 고 `GetOrders` 의 메서드는 `DataAccessTier` 프로젝트.

### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-customers-table"></a>데이터 액세스 계층에서 Customers 테이블을 반환하는 메서드를 만들려면

1.  **솔루션 탐색기**를 두 번 클릭 **NorthwindDataset.xsd** 를 데이터 집합을 엽니다.

2.  마우스 오른쪽 단추로 클릭 **CustomersTableAdapter** 누릅니다 **쿼리 추가**합니다.

3.  에 **명령 유형을 선택** 페이지에서 기본값을 그대로 둡니다 **사용 하 여 SQL 문을** 클릭 **다음**합니다.

4.  에 **쿼리 형식 선택** 페이지에서 기본값인 **행을 반환 하는 SELECT** 클릭 **다음**합니다.

5.  에 **SQL SELECT 문을 지정** 페이지에서 기본 쿼리를 그대로 두고 클릭 **다음**합니다.

6.  에 **생성할 메서드 선택** 페이지에서 입력 **GetCustomers** 에 대 한를 **메서드 이름** 에 **DataTable 반환** 섹션입니다.

7.  **마침**을 클릭합니다.

### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-orders-table"></a>데이터 액세스 계층에서 Orders 테이블을 반환하는 메서드를 만들려면

1.  마우스 오른쪽 단추로 클릭 **OrdersTableAdapter** 누릅니다 **쿼리 추가**합니다.

2.  에 **명령 유형을 선택** 페이지에서 기본값을 그대로 둡니다 **사용 하 여 SQL 문을** 클릭 **다음**합니다.

3.  에 **쿼리 형식 선택** 페이지에서 기본값인 **행을 반환 하는 SELECT** 클릭 **다음**합니다.

4.  에 **SQL SELECT 문을 지정** 페이지에서 기본 쿼리를 그대로 두고 클릭 **다음**합니다.

5.  에 **생성할 메서드 선택** 페이지에서 입력 **GetOrders** 에 대 한를 **메서드 이름** 에 **DataTable 반환** 섹션입니다.

6.  **마침**을 클릭합니다.

7.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

## <a name="add-a-reference-to-the-data-entity-and-data-access-tiers-to-the-data-service"></a>데이터 서비스에 데이터 엔터티에 대 한 참조 및 데이터 액세스 계층 추가
 데이터 서비스 데이터 집합 및 TableAdapters의 정보를 필요로 하므로 참조를 추가 합니다 **DataEntityTier** 하 고 **DataAccessTier** 프로젝트입니다.

### <a name="to-add-references-to-the-data-service"></a>데이터 서비스에 참조를 추가하려면

1.  마우스 오른쪽 단추로 클릭 **DataService** 에 **솔루션 탐색기** 누릅니다 **참조 추가**합니다.

2.  클릭 합니다 **프로젝트** 탭에 **참조 추가** 대화 상자.

3.  둘 다 선택 합니다 **DataAccessTier** 하 고 **DataEntityTier** 프로젝트입니다.

4.  **확인**을 클릭합니다.

## <a name="add-functions-to-the-service-to-call-the-getcustomers-and-getorders-methods-in-the-data-access-tier"></a>데이터 액세스 계층에서 GetCustomers 및 GetOrders 메서드를 호출 하려면 서비스에 함수 추가
 이제 데이터 액세스 계층에 데이터를 반환하는 메서드가 포함되었으므로 데이터 서비스에 데이터 액세스 계층의 메서드를 호출하는 메서드를 만듭니다.

> [!NOTE]
> C# 프로젝트의 경우 다음 코드가 컴파일하도록 할 `System.Data.DataSetExtensions` 어셈블리에 대한 참조를 추가해야 합니다.

### <a name="to-create-the-getcustomers-and-getorders-functions-in-the-data-service"></a>데이터 서비스에서 GetCustomers 및 GetOrders 함수를 만들려면

1.  에 **DataService** 프로젝트를 두 번 클릭 **IService1.vb** 하거나 **IService1.cs**합니다.

2.  아래에 다음 코드를 추가 합니다 **여기에 서비스 작업 추가** 주석:

    ```vb
    <OperationContract()> _
    Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable

    <OperationContract()> _
    Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable
    ```

    ```csharp
    [OperationContract]
    DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers();

    [OperationContract]
    DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders();
    ```

3.  DataService 프로젝트에서 두 번 클릭 **Service1.vb** (또는 **Service1.cs**).

4.  다음 코드를 추가 합니다 **Service1** 클래스:

    ```vb
    Public Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable Implements IService1.GetCustomers
        Dim CustomersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
        Return CustomersTableAdapter1.GetCustomers()
    End Function

    Public Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable Implements IService1.GetOrders
        Dim OrdersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
        Return OrdersTableAdapter1.GetOrders()
    End Function
    ```

    ```csharp
    public DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter
             CustomersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter();
        return CustomersTableAdapter1.GetCustomers();
    }
    public DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders()
    {
        DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter
             OrdersTableAdapter1
            = new DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter();
        return OrdersTableAdapter1.GetOrders();
    }
    ```

5.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

## <a name="create-a-presentation-tier-to-display-data-from-the-data-service"></a>데이터 서비스에서 데이터를 표시 하는 프레젠테이션 계층 만들기
 이제 솔루션에 포함 된 데이터를 호출 하는 메서드를 사용 하는 데이터 서비스 계층에 액세스, 데이터 서비스를 호출 하는 다른 프로젝트를 만들고을 사용자에 게 데이터를 표시. 이 연습에서는 N 계층 응용 프로그램의 표시 계층인 Windows Forms 응용 프로그램을 만듭니다.

### <a name="to-create-the-presentation-tier-project"></a>표시 계층 프로젝트를 만들려면

1.  솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** > **새 프로젝트**합니다.

2.  에 **새 프로젝트** 대화 상자의 왼쪽 창에서 선택 **Windows Desktop**합니다. 가운데 창에서 선택 **Windows Forms 앱**합니다.

3.  프로젝트 이름을 **PresentationTier** 누릅니다 **확인**합니다.

    PresentationTier 프로젝트가 만들어져 NTierWalkthrough 솔루션에 추가됩니다.

## <a name="set-the-presentationtier-project-as-the-startup-project"></a>PresentationTier 프로젝트를 시작 프로젝트로 설정
설정 된 **PresentationTier** 프로젝트를 솔루션에 대 한 시작 프로젝트를 제공 하 고 데이터와 상호 작용 하는 실제 클라이언트 응용 프로그램 이므로 합니다.

### <a name="to-set-the-new-presentation-tier-project-as-the-startup-project"></a>새 표시 계층 프로젝트를 시작 프로젝트로 설정 하려면

-   **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **PresentationTier** 누릅니다 **시작 프로젝트로 설정**합니다.

## <a name="add-references-to-the-presentation-tier"></a>프레젠테이션 계층에 대 한 참조를 추가 합니다.
 클라이언트 응용 프로그램 PresentationTier 데이터 서비스에 서비스 참조를 서비스의 메서드에 액세스 하기 위해 필요 합니다. WCF 서비스를 통한 형식 공유를 사용하도록 설정하려면 데이터 집합에 대한 참조도 필요합니다. 데이터 서비스를 통해 형식 공유를 설정 하기 전까지 부분 데이터 집합 클래스에 추가 하는 코드 프레젠테이션 계층에 사용할 수 없는 경우 일반적으로 행 및 열 변경 이벤트 데이터 테이블의 유효성 검사 코드 등의 코드를 추가 하기 때문에이 코드는 클라이언트에서 액세스 해야 가능성이 높습니다.

### <a name="to-add-a-reference-to-the-presentation-tier"></a>표시 계층에 대한 참조를 추가하려면

1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **PresentationTier** 선택한 **참조 추가**합니다.

2.  에 **참조 추가** 대화 상자를 선택 합니다 **프로젝트** 탭 합니다.

3.  선택 **DataEntityTier** 선택한 **확인**합니다.

### <a name="to-add-a-service-reference-to-the-presentation-tier"></a>표시 계층에 대한 서비스 참조를 추가하려면

1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **PresentationTier** 선택한 **서비스 참조 추가**합니다.

2.  에 **서비스 참조 추가** 대화 상자에서 **Discover**합니다.

3.  선택 **Service1** 선택한 **확인**합니다.

    > [!NOTE]
    > 여러 서비스를 현재 컴퓨터의 경우이 연습에서 이전에 만든 서비스를 선택 (포함 하는 서비스를 `GetCustomers` 고 `GetOrders` 메서드).

## <a name="add-datagridviews-to-the-form-to-display-the-data-returned-by-the-data-service"></a>Datagridview를 폼에 데이터 서비스에서 반환 된 데이터 표시 추가
 데이터 서비스에 대 한 서비스 참조를 추가 합니다 **데이터 원본** 창 서비스에서 반환 되는 데이터를 사용 하 여 자동으로 채워집니다.

### <a name="to-add-two-data-bound-datagridviews-to-the-form"></a>데이터 바인딩된 DataGridView 두 개를 폼에 추가하려면

1.  **솔루션 탐색기**를 선택 합니다 **PresentationTier** 프로젝트입니다.

2.  에 **데이터 원본** 창 확장 **NorthwindDataSet** 찾아서 합니다 **고객** 노드.

3.  끌기 합니다 **고객** 노드를 Form1 합니다.

4.  에 **데이터 원본** 창 확장를 **고객** 노드 관련 찾아서 **주문** 노드 (합니다 **주문** 노드에 중첩 된 합니다  **고객은** 노드).

5.  관련 끌어 **주문** 노드를 Form1 합니다.

6.  폼의 빈 영역을 두 번 클릭하여 `Form1_Load` 이벤트 처리기를 만듭니다.

7.  다음 코드를 `Form1_Load` 이벤트 처리기에 추가합니다.

    ```vb
    Dim DataSvc As New ServiceReference1.Service1Client
    NorthwindDataSet.Customers.Merge(DataSvc.GetCustomers)
    NorthwindDataSet.Orders.Merge(DataSvc.GetOrders)
    ```

    ```csharp
    ServiceReference1.Service1Client DataSvc =
        new ServiceReference1.Service1Client();
    northwindDataSet.Customers.Merge(DataSvc.GetCustomers());
    northwindDataSet.Orders.Merge(DataSvc.GetOrders());
    ```

## <a name="increase-the-maximum-message-size-allowed-by-the-service"></a>서비스에서 허용 되는 최대 메시지 크기를 늘리려면
에 대 한 기본값 `maxReceivedMessageSize` 에서 검색할 데이터를 저장 하기에 충분히 크지 않은 합니다 `Customers` 및 `Orders` 테이블입니다. 다음 단계에서는 값을 6553600으로 늘릴 수 있습니다. 서비스 참조를 자동으로 업데이트 하는 클라이언트에서 값을 변경 하는 경우.

> [!NOTE]
> 기본값이 작은 이유는 DoS(서비스 거부) 공격에 대한 노출을 제한하기 위해서입니다. 자세한 내용은 <xref:System.ServiceModel.WSHttpBindingBase.MaxReceivedMessageSize%2A>을 참조하십시오.

### <a name="to-increase-the-maxreceivedmessagesize-value"></a>maxReceivedMessageSize 값을 늘리려면

1.  **솔루션 탐색기**, 두 번 클릭 합니다 **app.config** 파일을 **PresentationTier** 프로젝트.

2.  찾을 합니다 **maxReceivedMessage** 크기 특성을 값으로 변경 `6553600`합니다.

## <a name="test-the-application"></a>응용 프로그램 테스트
키를 눌러 응용 프로그램을 실행 **F5**합니다. 데이터를 `Customers` 고 `Orders` 테이블 데이터 서비스에서 검색 되어 폼에 표시 합니다.

## <a name="next-steps"></a>다음 단계
 응용 프로그램 요구 사항에 따라 Windows 기반 응용 프로그램에서 관련 데이터를 저장한 후 몇 단계를 더 수행해야 할 수도 있습니다. 예를 들어 이 응용 프로그램을 다음과 같이 개선할 수 있습니다.

-   데이터 집합에 유효성 검사 기능을 추가합니다.

-   데이터를 데이터베이스로 다시 업데이트하기 위한 추가 메서드를 서비스에 추가합니다.

## <a name="see-also"></a>참고자료

- [n 계층 응용 프로그램에서 데이터 집합 작업](../data-tools/work-with-datasets-in-n-tier-applications.md)
- [계층적 업데이트](../data-tools/hierarchical-update.md)
- [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)