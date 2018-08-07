---
title: WCF 데이터 서비스에 WPF 컨트롤 바인딩
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 8823537c-82f0-41f7-bf30-705f0e5e59fd
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b3cd83a16ff3d497bd9e6a46f3a66a3d99506a1f
ms.sourcegitcommit: 3a11feebad45a0dd4ac45efcbfdf172fce46e1de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39582397"
---
# <a name="bind-wpf-controls-to-a-wcf-data-service"></a>WCF 데이터 서비스에 WPF 컨트롤 바인딩

이 연습에서는 데이터 바인딩된 컨트롤을 포함하는 WPF 응용 프로그램을 만듭니다. 컨트롤은 WCF 데이터 서비스에서 캡슐화 된 고객 레코드에 바인딩됩니다. 또한 고객이 레코드를 보고 업데이트하는 데 사용할 수 있는 단추도 추가합니다.

이 연습에서는 다음 작업을 수행합니다.

- AdventureWorksLT 샘플 데이터베이스의 데이터에서 생성되는 엔터티 데이터 모델을 만듭니다.

- WCF 데이터 서비스 만들기를 WPF 응용 프로그램 엔터티 데이터 모델의 데이터를 노출 합니다.

- 항목을 끌어 데이터 바인딩된 컨트롤의 집합을 만드는 합니다 **데이터 원본** 창에서 WPF 디자이너로 합니다.

- 고객 레코드를 앞뒤로 탐색하는 데 사용할 단추를 만듭니다.

- WCF Data Service 및 내부 데이터 소스 컨트롤의 데이터 변경 내용을 저장 하는 단추를 만듭니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

-   Visual Studio

-   AdventureWorksLT 샘플 데이터베이스가 연결된 SQL Server 또는 SQL Server Express의 실행 중인 인스턴스 액세스 권한. AdventureWorksLT 데이터베이스를 다운로드할 수 있습니다 합니다 [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)합니다.

또한 다음 개념에 대한 지식은 연습을 완료하는 데 반드시 필요하지는 않지만 사전에 파악해 두면 유용할 수 있습니다.

-   WCF Data Services. 자세한 내용은 [개요](/dotnet/framework/data/wcf/wcf-data-services-overview)합니다.

-   [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]의 데이터 모델

-   엔터티 데이터 모델 및 ADO.NET Entity Framework 자세한 내용은 [Entity Framework 개요](/dotnet/framework/data/adonet/ef/overview)합니다.

-   WPF 데이터 바인딩. 자세한 내용은 [데이터 바인딩 개요](/dotnet/framework/wpf/data/data-binding-overview)합니다.

## <a name="create-the-service-project"></a>서비스 프로젝트를 만들려면

WCF 데이터 서비스에 대 한 프로젝트를 만들어이 연습을 시작 합니다.

1.  Visual Studio를 시작합니다.

2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.

3.  확장 **Visual C#** 하거나 **Visual Basic**를 선택한 후 **웹**합니다.

4.  **ASP.NET 웹 응용 프로그램** 프로젝트 템플릿을 선택합니다.

5.  에 **이름을** 상자에 입력 **AdventureWorksService** 클릭 **확인**합니다.

     Visual Studio 만듭니다는 **AdventureWorksService** 프로젝트입니다.

6.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Default.aspx** 선택한 **삭제**합니다. 이 연습에서는 해당 파일이 필요하지 않습니다.

## <a name="create-an-entity-data-model-for-the-service"></a>서비스에 대 한 엔터티 데이터 모델 만들기

WCF 데이터 서비스를 사용 하 여 응용 프로그램에 데이터를 노출 하려면 서비스에 대 한 데이터 모델을 정의 해야 합니다. WCF Data Service는 두 가지 유형의 데이터 모델: 엔터티 데이터 모델 및 구현 하는 공용 언어 런타임 (CLR) 개체를 사용 하 여 정의 된 사용자 지정 데이터 모델을 <xref:System.Linq.IQueryable%601> 인터페이스입니다. 이 연습에서는 데이터 모델에 대해 엔터티 데이터 모델을 만듭니다.

1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.

2.  설치 된 템플릿 목록에서 클릭 **데이터**를 선택한 후는 **ADO.NET Entity Data Model** 프로젝트 항목입니다.

3.  이름을 변경할 `AdventureWorksModel.edmx`, 클릭 **추가**합니다.

     합니다 **엔터티 데이터 모델** 마법사가 열립니다.

4.  에 **Model 콘텐츠 선택** 페이지에서 클릭 **데이터베이스에서 생성**, 클릭 **다음**합니다.

5.  에 **데이터 연결 선택** 페이지에서 다음 옵션 중 하나를 선택 합니다.

    -   AdventureWorksLT 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.

    -   클릭 **새 연결**, AdventureWorksLT 데이터베이스에 대 한 연결을 만듭니다.

6.  에 **데이터 연결 선택** 페이지에서 확인 합니다 **으로 App.Config의 entity 연결 설정을 저장** 옵션을 선택한 다음 클릭 **다음**합니다.

7.  에 **데이터베이스 개체 선택** 페이지에서 **테이블**를 선택한 후는 **SalesOrderHeader** 테이블입니다.

8.  **마침**을 클릭합니다.

## <a name="create-the-service"></a>서비스 만들기

WPF 응용 프로그램 엔터티 데이터 모델에서 데이터를 노출 하는 WCF 데이터 서비스를 만듭니다.

1.  에 **프로젝트** 메뉴에서 **새 항목 추가**합니다.

2.  에 **설치 된 템플릿** 목록에서 **웹**를 선택한 후는 **WCF 데이터 서비스** 프로젝트 항목입니다.

3.  에 **이름을** 상자에 입력 `AdventureWorksService.svc`, 클릭 **추가**합니다.

     Visual Studio에 추가 된 `AdventureWorksService.svc` 프로젝트에.

## <a name="configure-the-service"></a>서비스 구성

사용자가 만든 엔터티 데이터 모델에서 작동 하도록 서비스를 구성 해야 합니다.

1.  에 `AdventureWorks.svc` 코드 파일에서 바꾸기 합니다 **AdventureWorksService** 클래스 선언을 다음 코드로 합니다.

     [!code-csharp[Data_WPFWCF#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_1.cs)]
     [!code-vb[Data_WPFWCF#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_1.vb)]

     이 코드는 업데이트를 **AdventureWorksService** 클래스에서 파생 되도록를 <xref:System.Data.Services.DataService%601> 에서 작동 하는 `AdventureWorksLTEntities` 개체 컨텍스트 클래스 엔터티 데이터 모델에 합니다. 또한 서비스의 클라이언트에 `InitializeService` 엔터티에 대한 모든 읽기/쓰기 권한을 허용하도록 `SalesOrderHeader` 메서드를 업데이트합니다.

2.  프로젝트를 빌드하고 오류가 없이 빌드되는지 확인합니다.

## <a name="create-the-wpf-client-application"></a>WPF 클라이언트 응용 프로그램 만들기

WCF 데이터 서비스에서 데이터를 표시 하려면 서비스를 기반으로 하는 데이터 소스를 사용 하 여 새 WPF 응용 프로그램을 만듭니다. 이 연습 뒷부분에서 응용 프로그램에 데이터 바인딩된 컨트롤을 추가합니다.

1.  **솔루션 탐색기**솔루션 노드를 마우스 오른쪽 단추로 클릭, 클릭 **추가**를 선택 하 고 **새 프로젝트**합니다.

2.  에 **새 프로젝트** 대화 상자에서 확장 **Visual C#** 또는 **Visual Basic**를 선택한 후 **Windows**합니다.

3.  선택 된 **WPF 응용 프로그램** 프로젝트 템플릿.

4.  에 **이름을** 상자에 입력 `AdventureWorksSalesEditor`, 클릭 **확인**합니다.

     Visual Studio에 추가 된 `AdventureWorksSalesEditor` 프로젝트를 솔루션입니다.

5.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.

     합니다 **데이터 원본** 창이 열립니다.

6.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.

     합니다 **데이터 원본 구성** 마법사가 열립니다.

7.  에 **데이터 소스 형식 선택** 마법사의 페이지 **서비스**를 클릭 하 고 **다음**합니다.

8.  에 **서비스 참조 추가** 대화 상자, 클릭 **Discover**합니다.

     Visual Studio는 사용 가능한 서비스에 대 한 현재 솔루션을 검색 하 고 추가 `AdventureWorksService.svc` 에서 사용 가능한 서비스 목록에는 **Services** 상자입니다.

9. 에 **Namespace** 상자에 입력 **AdventureWorksService**합니다.

10. 에 **Services** 상자를 클릭 합니다 **AdventureWorksService.svc**를 클릭 하 고 **확인**합니다.

     Visual Studio 서비스 정보를 다운로드 하 고 다음을 반환 합니다 **데이터 원본 구성** 마법사.

11. 에 **서비스 참조 추가** 페이지에서 클릭 **마침**합니다.

     Visual Studio 서비스에 의해 반환 되는 데이터를 나타내는 노드를 추가 합니다 **데이터 원본** 창입니다.

## <a name="define-the-user-interface"></a>사용자 인터페이스를 정의 합니다.

WPF 디자이너에서 XAML을 수정하여 창에 여러 단추를 추가합니다. 이 연습 뒷부분에서 사용자가 이러한 단추를 사용해 판매 레코드를 보고 업데이트할 수 있도록 하는 코드를 추가합니다.

1.  **솔루션 탐색기**를 두 번 클릭 **MainWindow.xaml**합니다.

     WPF 디자이너에서 창이 열립니다.

2.  디자이너의 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] 뷰에서 `<Grid>` 태그 사이에 다음 코드를 추가합니다.

    ```xaml
    <Grid.RowDefinitions>
        <RowDefinition Height="75" />
        <RowDefinition Height="525" />
    </Grid.RowDefinitions>
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>
    ```

3.  프로젝트를 빌드합니다.

## <a name="create-the-data-bound-controls"></a>데이터 바인딩된 컨트롤 만들기

끌어 고객 레코드를 표시 하는 컨트롤을 만들 합니다 `SalesOrderHeaders` 에서 노드를 **데이터 원본** 창에서 디자이너로 합니다.

1.  에 **데이터 원본** 창 드롭다운 메뉴를 클릭 합니다 **SalesOrderHeaders** 노드를 선택한 **세부 정보**합니다.

2.  확장 된 **SalesOrderHeaders** 노드.

3.  예를 들어 일부 필드 표시 되지 것입니다, 따라서 다음 노드 옆에 있는 드롭다운 메뉴를 클릭 하 고 선택 **None**:

    -   **CreditCardApprovalCode**

    -   **수정한 날짜**

    -   **OnlineOrderFlag**

    -   **RevisionNumber**

    -   **rowguid**

    이 작업을 수행하면 다음 단계에서 이러한 노드에 대해 데이터 바인딩된 컨트롤이 작성되지 않습니다. 이 연습에서는 최종 사용자는이 데이터를 볼 필요가 없습니다를 가정 합니다.

4.  **데이터 원본** 창에서 끌어 합니다 **SalesOrderHeaders** 단추가 포함 된 행 아래 표에서 행으로 노드.

     Visual Studio에서 XAML 및 데이터에 바인딩되는 컨트롤 집합을 만드는 코드를 생성 합니다 **제품** 테이블입니다. 생성 된 XAML 및 코드에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 데이터를 바인딩할 WPF 컨트롤](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)합니다.

5.  디자이너에서 텍스트 상자 옆에 클릭 합니다 **고객 ID** 레이블.

6.  에 **속성** 창에서 옆에 확인란 합니다 **IsReadOnly** 속성.

7.  설정 된 **IsReadOnly** 각 다음 텍스트 상자에 대 한 속성:

    -   **구매 주문 번호**

    -   **판매 주문 ID**

    -   **판매 주문 번호**

## <a name="load-the-data-from-the-service"></a>서비스에서 데이터를 로드 합니다.

서비스 프록시 개체를 사용 하 여 서비스에서 판매 데이터를 로드 합니다. 그런 다음 반환된 된 데이터에 대 한 데이터 원본에 할당 된 <xref:System.Windows.Data.CollectionViewSource> WPF 창에서.

1.  디자이너를 만들려면 합니다 `Window_Loaded` 이벤트 처리기를 텍스트를 두 번 클릭: **MainWindow**합니다.

2.  이벤트 처리기를 다음 코드로 바꿉니다. 바꿔야 하는 *localhost* 개발 컴퓨터에 로컬 호스트 주소를 사용 하 여이 코드의 주소입니다.

     [!code-csharp[Data_WPFWCF#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_2.cs)]
     [!code-vb[Data_WPFWCF#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_2.vb)]

## <a name="navigate-sales-records"></a>판매 레코드 탐색

사용자가 사용 하 여 판매 레코드를 스크롤할 수 있는 코드를 추가 합니다 **\<** 하 고 **>** 단추입니다.

1.  디자이너에서 두 번 클릭 합니다 **<** 창 화면에서 단추입니다.

     Visual Studio의 코드 숨김 파일이 열리고 새 `backButton_Click` 에 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.

2.  다음 코드를 생성된 `backButton_Click` 이벤트 처리기에 추가합니다.

     [!code-csharp[Data_WPFWCF#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_3.cs)]
     [!code-vb[Data_WPFWCF#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_3.vb)]

3.  디자이너로 돌아가서 두 번 클릭 합니다 **>** 단추입니다.

     Visual Studio의 코드 숨김 파일이 열리고 새 `nextButton_Click` 에 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.

4.  다음 코드를 생성된 `nextButton_Click` 이벤트 처리기에 추가합니다.

     [!code-csharp[Data_WPFWCF#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_4.cs)]
     [!code-vb[Data_WPFWCF#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_4.vb)]

## <a name="save-changes-to-sales-records"></a>판매 레코드 변경 내용을 저장합니다

보기를 사용 하 여 판매 레코드 변경 내용을 저장할 수 있게 해 주는 코드를 추가 합니다 **변경 내용을 저장** 단추:

1.  디자이너에서 두 번 클릭 합니다 **변경 내용 저장** 단추입니다.

     Visual Studio의 코드 숨김 파일이 열리고 새 `saveButton_Click` 에 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.

2.  다음 코드를 `saveButton_Click` 이벤트 처리기에 추가합니다.

     [!code-csharp[Data_WPFWCF#5](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_5.cs)]
     [!code-vb[Data_WPFWCF#5](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_5.vb)]

## <a name="test-the-application"></a>응용 프로그램 테스트

작성 하 고 볼 수 있으며 고객 레코드를 업데이트를 확인 하려면 응용 프로그램을 실행 합니다.

1.  **빌드합니다** 메뉴에서 클릭 **솔루션 빌드**합니다. 솔루션이 오류 없이 빌드되는지 확인합니다.

2.  키를 눌러 **Ctrl**+**F5**합니다.

     Visual Studio를 시작 합니다 **AdventureWorksService** 디버그 하지 않고 프로젝트입니다.

3.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **AdventureWorksSalesEditor** 프로젝트입니다.

4.  상황에 맞는 메뉴에서 **디버그**, 클릭 **새 인스턴스 시작**합니다.

     응용 프로그램이 실행됩니다. 다음 사항을 확인합니다.

    -   판매 주문 ID를 가진 첫 번째 판매 레코드에서 데이터의 다른 필드를 표시 하는 입력란 **71774**합니다.

    -   클릭할 수는 **>** 또는 **<** 단추 다른 판매 레코드를 탐색할 수 있습니다.

5.  판매 레코드 중 하나에서 일부 텍스트를 입력 합니다 **주석** 상자를 선택한 다음 클릭 **변경 내용 저장**합니다.

6.  응용 프로그램을 닫았다가 Visual Studio에서 다시 시작합니다.

7.  변경한 판매 레코드로 이동하여 응용 프로그램을 닫았다가 다시 열어도 변경 내용이 그대로 유지되는지 확인합니다.

8.  응용 프로그램을 닫습니다.

## <a name="next-steps"></a>다음 단계

이 연습을 완료하고 나면 다음과 같은 관련 작업을 수행할 수 있습니다.

-   사용 방법 알아보기 합니다 **데이터 원본** 다른 유형의 데이터 원본에 컨트롤을 WPF 바인딩할 Visual Studio의 창. 자세한 내용은 [데이터 집합에 바인딩할 WPF 컨트롤](../data-tools/bind-wpf-controls-to-a-dataset.md)합니다.

-   사용 방법 알아보기 합니다 **데이터 원본** WPF 컨트롤에 관련된 데이터 (즉, 부모-자식 관계에서 데이터)를 표시 하려면 Visual Studio의 창. 자세한 내용은 [연습: WPF 응용 프로그램에서 관련된 데이터 표시](../data-tools/display-related-data-in-wpf-applications.md)합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [데이터 집합으로 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-dataset.md)
- [WCF 개요 (.NET Framework)](/dotnet/framework/data/wcf/wcf-data-services-overview)
- [Entity Framework 개요 (.NET Framework)](/dotnet/framework/data/adonet/ef/overview)
- [데이터 바인딩 개요 (.NET Framework)](/dotnet/framework/wpf/data/data-binding-overview)