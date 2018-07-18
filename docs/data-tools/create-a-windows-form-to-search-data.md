---
title: 데이터 검색을 위한 Windows Form 만들기
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Windows Forms, searching data
- Windows Forms, displaying data
- parameters, displaying filtered data
- data [Visual Studio], parameterizing queries
- data [Visual Studio], searching
ms.assetid: 65ca79a9-7458-466c-af55-978cd24c549e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: cdc82db1f701abb26b983fe0a1f2e4c7752c6c55
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756401"
---
# <a name="create-a-windows-form-to-search-data"></a>데이터 검색을 위한 Windows Form 만들기
일반적인 응용 프로그램 시나리오에서는 선택한 데이터를 폼에 표시합니다. 특정 고객의 주문이나 특정 주문의 정보를 표시하려는 경우를 예로 들 수 있습니다. 이 시나리오에서는 사용자가 폼에 정보를 입력하면 해당 사용자의 입력을 매개 변수로 사용하여 쿼리가 실행됩니다. 즉 매개 변수가 있는 쿼리를 기준으로 데이터가 선택됩니다. 쿼리는 사용자가 입력한 기준을 만족하는 데이터만 반환합니다. 이 연습에서는 특정 구/군/시의 고객을 반환하는 쿼리를 만들고 사용자 인터페이스를 수정하여, 사용자가 구/군/시 이름을 입력한 후 단추를 눌러 쿼리를 실행할 수 있도록 하는 방법을 보여줍니다.

 매개 변수가 있는 쿼리를 사용하면 데이터베이스가 레코드를 빠르게 필터링하도록 함으로써 응용 프로그램의 효율성을 높일 수 있습니다. 반면 전체 데이터베이스 테이블을 요청 하 고 네트워크를 통해 전송 하는 데 한 다음 응용 프로그램 논리를 사용 하 여 원하는 레코드를 찾는 데 느리고 비효율적인 응용 프로그램이 될 수 있습니다.

 모든 TableAdapter (및 컨트롤 매개 변수 값을 허용 하 여 쿼리를 실행)를 사용 하 여 매개 변수가 있는 쿼리를 추가할 수 있습니다 합니다 **검색 조건 작성기** 대화 상자. 선택 하 여 대화 상자를 엽니다는 **쿼리 추가** 명령 합니다 **데이터** 메뉴 (또는 TableAdapter 스마트 태그).

 이 연습에서 설명하는 작업은 다음과 같습니다.

-   새로 만들 **Windows Forms 응용 프로그램** 프로젝트입니다.

-   만들기 및 사용 하 여 응용 프로그램에서 데이터 소스를 구성 합니다 **데이터 원본 구성** 마법사.

-   에 있는 항목의 삭제 유형을 설정 합니다 **데이터 원본** 창입니다.

-   항목을 끌어 데이터를 표시 하는 컨트롤 만들기 합니다 **데이터 원본** 창에서 폼입니다.

-   폼에 데이터를 표시하기 위한 컨트롤을 추가합니다.

-   완료 합니다 **검색 조건 작성기** 대화 상자.

-   폼에 매개 변수를 입력 하 고 매개 변수가 있는 쿼리를 실행 합니다.

## <a name="prerequisites"></a>전제 조건

이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.

1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 합니다 **Visual Studio 설치 관리자**합니다. 에 **Visual Studio 설치 관리자**의 일부로 설치 SQL Server Express LocalDB를 수 있습니다 합니다 **데이터 저장 및 처리** 워크 로드 또는 개별 구성 요소로.

2.  다음이 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.

    1. Visual Studio에서 엽니다는 **SQL Server 개체 탐색기** 창입니다. (SQL Server 개체 탐색기의 일부로 설치 됩니다 합니다 **데이터 저장소 및 처리** 워크 로드에는 **Visual Studio 설치 관리자**.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리**합니다.

       쿼리 편집기 창이 열립니다.

    2. 복사 합니다 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 클립보드에 있습니다. 이 T-SQL 스크립트부터에서 Northwind 데이터베이스를 만들고 데이터로 채웁니다.

    3. T-SQL 스크립트, 쿼리 편집기에 붙여넣고 선택한 합니다 **Execute** 단추입니다.

       짧은 시간 후 쿼리 실행이 완료 하 고 Northwind 데이터베이스 생성 됩니다.

## <a name="create-the-windows-forms-application"></a>Windows Forms 응용 프로그램 만들기
 첫 번째 단계를 만드는 것을 **Windows Forms 응용 프로그램**합니다. 프로젝트에 이름을 할당 하는 것은이 단계에서 선택 사항 이지만 이름을 지정 하겠습니다 것를 여기서 나중에 프로젝트를 저장할 수 있으므로 합니다.

#### <a name="to-create-the-new-windows-forms-application-project"></a>새 Windows Forms 응용 프로그램 프로젝트를 만들려면

1. Visual Studio에서에 **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.

2. 확장 **Visual C#** 하거나 **Visual Basic** 왼쪽 창에서 선택한 **Windows Desktop**합니다.

3. 가운데 창에서 선택 합니다 **Windows Forms 앱** 형식 프로젝션 합니다.

4. 프로젝트 이름을 **WindowsSearchForm**를 선택한 후 **확인**합니다.

     합니다 **WindowsSearchForm** 프로젝트에 추가한 생성 **솔루션 탐색기**합니다.

## <a name="create-the-data-source"></a>데이터 원본 만들기
이 단계 사용 하 여 데이터베이스에서 데이터 원본을 만듭니다는 **데이터 원본 구성** 마법사.

#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면

1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.

2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성** 마법사.

3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스** 를 선택하고 **다음**을 클릭합니다.

4.  에 **데이터 연결 선택** 페이지 중 하나를 수행 합니다.

    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.

    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자.

5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 클릭 옵션을 선택 **다음**합니다.

6.  에 **응용 프로그램 구성 파일에 연결 문자열을 저장** 페이지에서 클릭 **다음**합니다.

7.  에 **데이터베이스 개체 선택** 페이지에서 확장을 **테이블** 노드.

8.  선택 된 **고객** 테이블을 마우스 클릭 **마침**합니다.

     합니다 **NorthwindDataSet** 프로젝트에 추가 됩니다 및 **고객** 테이블에 표시 됩니다는 **데이터 원본** 창입니다.

## <a name="create-the-form"></a>폼을 만들려면
 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수는 **데이터 원본** 창에서 폼으로 합니다.

#### <a name="to-create-data-bound-controls-on-the-form"></a>폼에서 데이터 바인딩된 컨트롤을 만들려면

1.  확장 된 **고객** 에서 노드를 **데이터 원본** 창.

2.  끌기 합니다 **고객** 에서 노드를 **데이터 원본** 창에서 폼으로 합니다.

     <xref:System.Windows.Forms.DataGridView>와 레코드 탐색에 사용되는 도구 스트립(<xref:System.Windows.Forms.BindingNavigator>)이 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter를 <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.

## <a name="add-parameterization-search-functionality-to-the-query"></a>쿼리를 매개 변수화 (검색 기능) 추가
 사용 하 여 원래 쿼리에 WHERE 절을 추가할 수는 **검색 조건 작성기** 대화 상자.

#### <a name="to-create-a-parameterized-query-and-controls-to-enter-the-parameters"></a>매개 변수가 있는 쿼리와 컨트롤을 만들어 매개 변수를 입력하려면

1.  선택 된 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **쿼리 추가** 에 **데이터** 메뉴.

2.  형식 `FillByCity` 에 **새 쿼리 이름** 영역에는 **검색 조건 작성기** 대화 상자.

3.  추가 `WHERE City = @City` 에서 쿼리를 **쿼리 텍스트** 영역입니다.

     이 쿼리는 다음과 같아야 합니다.

     ```sql
     SELECT CustomerID, CompanyName, ContactName, ContactTitle,
          Address, City, Region, PostalCode, Country, Phone, Fax
     FROM Customers
     WHERE City = @City
     ```

    > [!NOTE]
    >  물음표를 사용 하는 액세스 및 OLE DB 데이터 원본 ('? ')에 매개 변수를 표기 하므로 WHERE 절은 다음과 같습니다: `WHERE City = ?`합니다.

4.  클릭 **확인** 닫으려면 합니다 **검색 조건 작성기** 대화 상자.

     A **FillByCityToolStrip** 폼에 추가 됩니다.

## <a name="testing-the-application"></a>응용 프로그램 테스트
 폼 열리고 준비 하면 매개 변수 입력으로 사용 하면 응용 프로그램을 실행 합니다.

#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면

1.  **F5** 키를 눌러 응용 프로그램을 실행합니다.

2.  형식 **런던** 에 **City** 텍스트 상자를 클릭 한 다음 **FillByCity**합니다.

     데이터 그리드 조건을 충족 하는 고객으로 채워집니다. 이 예제에서는 데이터 표에 표시의 값이 있는 고객 **런던** 에서 자신의 **City** 열입니다.

## <a name="next-steps"></a>다음 단계
 응용 프로그램 요구 사항에 따라 매개 변수가 있는 폼을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다. 이 연습에서 보완할 수 있는 사항은 다음과 같습니다.

-   관련 데이터를 표시하는 컨트롤을 추가합니다. 자세한 내용은 [데이터 집합의 관계](relationships-in-datasets.md)합니다.

-   데이터 집합을 편집하여 데이터베이스 개체를 추가하거나 편집합니다. 자세한 내용은 [데이터 집합 만들기 및 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)을 참조하세요.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)