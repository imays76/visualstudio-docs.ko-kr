---
title: '연습: WPF 및 Entity Framework를 사용 하 여 WCF 데이터 서비스 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data services in Visual Studio
- WCF Data Services, Visual Studio
- ADO.NET Data Services, Visual Studio
- WCF data services in Visual Studio
ms.assetid: da66ad1b-a25d-485c-af13-2d18f0422e3d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 082fe68979ea7ae6a0c0655b7731aa8c7c9f3ac5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49838766"
---
# <a name="walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework"></a>연습: WPF 및 Entity Framework를 사용 하 여 WCF 데이터 서비스 만들기
이 연습에는 간단한을 만드는 방법을 보여 줍니다 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] 에서 호스팅되는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램 및 Windows Forms 응용 프로그램에서 액세스 합니다.

이 연습에 있습니다.

- 호스트에 웹 응용 프로그램을 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]입니다.

- 만들기는 [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] 나타내는 `Customers` Northwind 데이터베이스의 테이블입니다.

- [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]를 만듭니다.

- 클라이언트 응용 프로그램을 만들고 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]에 대한 참조를 추가합니다.

- 서비스에 대한 데이터 바인딩을 활성화하고 사용자 인터페이스를 생성합니다.

- 필요한 경우 응용 프로그램에 필터링 기능을 추가합니다.

## <a name="prerequisites"></a>전제 조건
이 연습에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다.

1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 합니다 **Visual Studio 설치 관리자**합니다. 에 **Visual Studio 설치 관리자**의 일부로 SQL Server Express LocalDB를 설치할 수 있습니다는 **데이터 저장 및 처리** 워크 로드 또는 개별 구성 요소로 합니다.

2.  다음이 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.

    1. Visual Studio에서 엽니다는 **SQL Server 개체 탐색기** 창입니다. (**SQL Server 개체 탐색기** 의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리**합니다.

       쿼리 편집기 창이 열립니다.

    2. 복사 합니다 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 클립보드에 있습니다. 이 T-SQL 스크립트부터에서 Northwind 데이터베이스를 만들고 데이터로 채웁니다.

    3. T-SQL 스크립트, 쿼리 편집기에 붙여넣고 선택한 합니다 **Execute** 단추입니다.

       짧은 시간 후 쿼리 실행이 완료 하 고 Northwind 데이터베이스 생성 됩니다.

## <a name="creating-the-service"></a>서비스 만들기
만들려는 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], 추가 웹 프로젝트를 만들기는 [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]을 만든 다음 모델에서 서비스 합니다.

첫 번째 단계에서는 서비스를 호스팅할 웹 프로젝트를 추가할 수 있습니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-the-web-project"></a>웹 프로젝트를 만들려면

1.  메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

2.  에 **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **Visual C#** 및 **웹** 노드를 선택한 후는 **ASP 합니다. NET 웹 응용 프로그램** 템플릿.

3.  에 **이름** 텍스트 상자에 입력 합니다 **NorthwindWeb**를 선택한 후는 **확인** 단추입니다.

4.  에 **새 ASP.NET 프로젝트** 대화 상자의 **템플릿을 선택** 목록에서 선택 **빈**를 선택한 후는 **확인** 단추.

만든 다음 단계는 [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] 나타내는 `Customers` Northwind 데이터베이스의 테이블입니다.

### <a name="to-create-the-entity-data-model"></a>엔터티 데이터 모델을 만들려면

1.  메뉴 모음에서 **프로젝트** > **새 항목 추가**를 선택합니다.

2.  에 **새 항목 추가** 대화 상자를 선택 합니다 **데이터** 노드를 선택한 후는 **ADO.NET 엔터티 데이터 모델** 항목.

3.  에 **이름** 텍스트 상자에 입력 합니다 `NorthwindModel`를 선택한 후는 **추가** 단추입니다.

     엔터티 데이터 모델 마법사가 나타납니다.

4.  엔터티 데이터 모델 마법사에서에 **Model 콘텐츠 선택** 페이지를 선택 합니다 **데이터베이스의 EF 디자이너** 항목을 선택한 후는 **다음** 단추.

5.  **데이터 연결 선택** 페이지에서 다음 단계 중 하나를 수행합니다.

    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.

         또는

    -   선택 된 **새 연결** 단추는 새 데이터 연결을 구성 합니다. 자세한 내용은 [새 연결 추가](../data-tools/add-new-connections.md)합니다.

6.  데이터베이스에서 암호를 요구 하는 경우 선택 합니다 **예, 연결 문자열에 중요 한 데이터를 포함** 옵션 단추를 선택한 후 합니다 **다음** 단추입니다.

    > [!NOTE]
    > 선택 대화 상자가 나타나면 **예** 프로젝트에는 파일을 저장 합니다.

7.  에 **버전을 선택** 페이지를 선택 합니다 **Entity Framework 5.0** 옵션 단추를 선택한 후는 **다음** 단추.

    > [!NOTE]
    > WCF 서비스를 사용 하 여 최신 버전의 Entity Framework 6을 사용 하려면 WCF Data Services Entity Framework 공급자 NuGet 패키지를 설치 해야 합니다. 참조 [WCF 데이터를 사용 하 여 Entity Framework 6을 사용 하 여 5.6.0 Services](https://blogs.msdn.microsoft.com/odatateam/2013/10/02/using-wcf-data-services-5-6-0-with-entity-framework-6/)합니다.

8.  에 **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 선택 합니다 **고객** 확인란을 선택한 후는 **마침** 단추입니다.

     엔터티 모델 다이어그램이 표시와 *NorthwindModel.edmx* 파일이 프로젝트에 추가 됩니다.

다음 단계를 만들고 데이터 서비스를 테스트 합니다.

### <a name="to-create-the-data-service"></a>데이터 서비스를 만들려면

1.  메뉴 모음에서 **프로젝트** > **새 항목 추가**를 선택합니다.

2.  에 **새 항목 추가** 대화 상자를 선택 합니다 **웹** 노드를 선택한 후는 **WCF Data Service 5.6** 항목.

3.  에 **이름** 텍스트 상자에 입력 합니다 `NorthwindCustomers`를 선택한 후는 **추가** 단추입니다.

     **NorthwindCustomers.svc** 파일에 표시 합니다 **코드 편집기**합니다.

4.  에 **코드 편집기**, 찾은 첫 번째 `TODO:` 주석 및 코드를 다음으로 바꿉니다.

     [!code-vb[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.cs)]

5.  `InitializeService` 이벤트 처리기의 주석을 다음 코드로 바꿉니다.

     [!code-vb[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.cs)]

6.  메뉴 모음에서 **디버깅할** > **디버깅 하지 않고 시작** 서비스를 실행 합니다. 브라우저 창이 열리고 서비스에 대 한 XML 스키마에 표시 됩니다.

7.  에 **주소** 막대에서 입력 `Customers` 에 대 한 URL의 끝 **NorthwindCustomers.svc**를 선택한 후는 **Enter** 키.

     에 있는 데이터의 XML 표현을 `Customers` 테이블이 나타납니다.

    > [!NOTE]
    > Internet Explorer가 이 데이터를 RSS 피드로 잘못 해석하는 경우도 있습니다. RSS 피드를 표시하는 옵션은 반드시 비활성화되어 있어야 합니다. 자세한 내용은 [서비스 참조 문제 해결](../data-tools/troubleshooting-service-references.md)합니다.

8.  브라우저 창을 닫습니다.

다음 단계에서는 서비스를 사용할 Windows Forms 클라이언트 응용 프로그램을 만들 수 있습니다.

## <a name="creating-the-client-application"></a>클라이언트 응용 프로그램 만들기
 클라이언트 응용 프로그램을 만들려면 추가 두 번째 프로젝트, 프로젝트에 대 한 서비스 참조 추가, 데이터 원본을 구성 하 고 만들 서비스의 데이터를 표시 하기 위한 사용자 인터페이스입니다.

 첫 단계로, Windows Forms 프로젝트를 솔루션에 추가 하 고 시작 프로젝트로 설정 합니다.

### <a name="to-create-the-client-application"></a>클라이언트 응용 프로그램을 만들려면

1.  메뉴 모음에서 파일을 선택 **추가** > **새 프로젝트**합니다.

2.  에 **새 프로젝트** 대화 상자에서 합니다 **Visual Basic** 또는 **Visual C#** 노드를 선택 합니다 **Windows** 노드를를 선택한 다음  **Windows Forms 응용 프로그램**합니다.

3.  **이름** 텍스트 상자에 `NorthwindClient`를 입력하고 **확인** 단추를 선택합니다.

4.  **솔루션 탐색기**를 선택 합니다 **NorthwindClient** 프로젝트 노드.

5.  메뉴 모음에서 선택 **프로젝트**하십시오 **시작 프로젝트로 설정**합니다.

다음 단계에 대 한 서비스 참조 추가 [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] 웹 프로젝트에서.

### <a name="to-add-a-service-reference"></a>서비스 참조를 추가하려면

1.  메뉴 모음에서 선택 **프로젝트** > **서비스 참조 추가**합니다.

2.  에 **서비스 참조 추가** 대화 상자를 선택 합니다 **검색** 단추입니다.

     NorthwindCustomers 서비스의 URL에 표시 된 **주소** 필드입니다.

3.  선택 된 **확인** 서비스 참조를 추가 하는 단추입니다.

다음 단계에서는 서비스에 대 한 데이터 바인딩을 사용할 수 있도록 데이터 원본을 구성할 수 있습니다.

### <a name="to-enable-data-binding-to-the-service"></a>서비스에 대한 데이터 바인딩을 사용하려면

1.  메뉴 모음에서 선택 **뷰** > **기타 Windows** > **데이터 원본을**합니다.

2.  에 **데이터 원본** 창 선택 합니다 **새 데이터 소스 추가** 단추입니다.

3.  에 **데이터 소스 형식 선택** 페이지를 **데이터 소스 구성 마법사**, 선택 **개체**를 선택한 후 합니다 **다음** 단추 .

4.  에 **데이터 개체 선택** 페이지에서 **NorthwindClient** 노드를 펼친 다음 합니다 **NorthwindClient.ServiceReference1** 노드.

5.  선택 **고객** 확인란을 선택한 다음를 선택 합니다 **마침** 단추입니다.

다음 단계에서는 서비스에서 데이터를 표시 하는 사용자 인터페이스를 만들 수 있습니다.

### <a name="to-create-the-user-interface"></a>사용자 인터페이스를 만들려면

1. 에 **데이터 원본** 창에 대 한 바로 가기 메뉴를 열고는 **고객** 노드 선택 **복사**합니다.

2. 에 **Form1.vb** 하거나 **Form1.cs** 폼 디자이너에서 바로 가기 메뉴를 열고 선택한 **붙여넣기**합니다.

    <xref:System.Windows.Forms.DataGridView> 컨트롤, <xref:System.Windows.Forms.BindingSource> 구성 요소 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소가 폼에 추가됩니다.

3. 선택 합니다 **CustomersDataGridView** 컨트롤을 한 다음는 **속성** 창 집합을 **도킹** 속성을 **입력**.

4. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 합니다 **Form1** 노드 선택 **코드 보기** 코드 편집기를 열고 다음 코드를 추가 `Imports` 또는 `Using`파일의 맨 위에 있는 문.

   ```vb
   Imports NorthwindClient.ServiceReference1
   ```

   ```csharp
   using NorthwindClient.ServiceReference1;
   ```

5. 다음 코드를 `Form1_Load` 이벤트 처리기에 추가합니다.

   ```vb
   Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
           Dim proxy As New NorthwindEntities _
   (New Uri("http://localhost:53161/NorthwindCustomers.svc/"))
           Me.CustomersBindingSource.DataSource = proxy.Customers
       End Sub
   ```

   ```csharp
   private void Form1_Load(object sender, EventArgs e)
   {
   NorthwindEntities proxy = new NorthwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc/"));
   this.CustomersBindingSource.DataSource = proxy.Customers;
   }
   ```

6. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 합니다 **NorthwindCustomers.svc** 파일을 선택 **브라우저에서 보기**합니다. Internet Explorer가 열리고 서비스에 대 한 XML 스키마에 표시 됩니다.

7. Internet Explorer 주소 표시줄에서 URL을 복사합니다.

8. 4단계에서 추가한 코드에서 `http://localhost:53161/NorthwindCustomers.svc/`를 선택하여 방금 복사한 URL로 바꿉니다.

9. 메뉴 모음에서 선택 **디버깅할** > **디버깅 시작** 응용 프로그램을 실행 합니다. 고객 정보가 표시 됩니다.

   이제 NorthwindCustomers 서비스의 고객 목록을 표시하는 응용 프로그램이 만들어졌습니다. 이 서비스를 통해 추가 데이터를 노출하려면 Northwind 데이터베이스의 다른 테이블을 포함하도록 [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]을 수정하면 됩니다.

다음 선택적 단계에서는 서비스에서 반환 되는 데이터를 필터링 하는 방법을 배웁니다.

## <a name="adding-filtering-capabilities"></a>필터링 기능 추가
 이 단계에서는 고객의 도시 데이터를 필터링 하도록 응용 프로그램 사용자 지정 합니다.

### <a name="to-add-filtering-by-city"></a>구/군/시 기준 필터링을 추가하려면

1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 합니다 **Form1.vb** 또는 **Form1.cs** 노드 선택 **엽니다**합니다.

2.  추가 <xref:System.Windows.Forms.TextBox> 컨트롤 및 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 폼입니다.

3.  바로 가기 메뉴를 열고 합니다 <xref:System.Windows.Forms.Button> 컨트롤을 선택 **코드 보기**에서 다음 코드를 추가 하 고는 `Button1_Click` 이벤트 처리기:

    ```vb
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
            Dim proxy As New northwindEntities _
    (New Uri("http://localhost:53161/NorthwindCustomers.svc"))
            Dim city As String = TextBox1.Text

            If city <> "" Then
                Me.CustomersBindingSource.DataSource = From c In _
             proxy.Customers Where c.City = city
            End If

        End Sub
    ```

    ```csharp
    private void Button1_Click(object sender, EventArgs e)
    {
    ServiceReference1.northwindModel.northwindEntities proxy = new northwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc"));
    string city = TextBox1.Text;

    if (!string.IsNullOrEmpty(city)) {
    this.CustomersBindingSource.DataSource = from c in proxy.Customers where c.City == city;
    }

    }
    ```

4.  앞의 코드에서 `http://localhost:53161/NorthwindCustomers.svc`를 `Form1_Load` 이벤트 처리기의 URL로 바꿉니다.

5.  메뉴 모음에서 선택 **디버깅할** > **디버깅 시작** 응용 프로그램을 실행 합니다.

6.  텍스트 상자에 입력 **런던**, 한 다음 단추를 선택 합니다. London의 고객만 표시됩니다.

## <a name="see-also"></a>참고자료

- [Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
- [방법: 추가, 업데이트 또는 WCF 데이터 서비스 참조를 제거 합니다.](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)