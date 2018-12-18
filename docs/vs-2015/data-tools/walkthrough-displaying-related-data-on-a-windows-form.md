---
title: '연습: Windows Form에 관련된 데이터 표시 | Microsoft Docs'
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
- displaying data on forms, walkthroughs
- Windows Forms, displaying data
- data [Visual Studio], displaying on Windows Forms
- master-details lists, displaying on Windows Forms
- data [Visual Studio], master-details
- displaying tables, related data
- displaying table data
- displaying table information
ms.assetid: fc4b9055-2bf3-4028-8aad-9489820d69f6
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 882c8229c105920efe247a54e9525a262e6a3246
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49282674"
---
# <a name="walkthrough-displaying-related-data-on-a-windows-form"></a>연습: Windows Form에 관련 데이터 표시
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

대부분의 응용 프로그램 시나리오에서는 테이블 두 개 이상의 데이터를 사용하며 관련 테이블의 데이터를 사용하는 경우도 많습니다. 이러한 경우에는 부모-자식 관계를 사용하게 됩니다. 고객 레코드를 선택하면 해당 고객의 주문이 표시되는 폼을 만드는 경우를 예로 들 수 있습니다. 이 경우 자식 <xref:System.Windows.Forms.BindingSource.DataSource%2A>의 <xref:System.Windows.Forms.BindingSource> 속성을 자식 테이블이 아닌 부모 <xref:System.Windows.Forms.BindingSource>로 설정하고 자식 <xref:System.Windows.Forms.BindingSource.DataMember%2A>의 <xref:System.Windows.Forms.BindingSource> 속성을 부모 및 자식 테이블을 함께 연결하는 데이터 관계로 설정하여 폼에 관련 레코드를 표시합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   만들기는 **Windows 응용 프로그램** 프로젝트입니다.  
  
-   기반 만들고 응용 프로그램에서 데이터 집합을 구성 합니다 `Customers` 및 `Orders` 사용 하 여 Northwind 데이터베이스의 테이블을 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)합니다.  
  
-   `Customers` 테이블의 데이터를 표시하기 위한 컨트롤을 추가합니다.  
  
-   선택된 `Orders`를 기준으로 `Customer`를 표시하기 위한 컨트롤을 추가합니다.  
  
-   각 고객을 선택하고 선택한 고객에 대해 올바른 주문이 표시되는지 확인하는 방식으로 응용 프로그램을 테스트합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스. 예제 데이터베이스 설치를 참조 하세요 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계를 만드는 것을 **Windows 응용 프로그램**합니다.  
  
#### <a name="to-create-the-windows-application-project"></a>Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로젝트 이름을 `RelatedDataWalkthrough`로 지정합니다.  
  
3.  선택 **Windows 응용 프로그램** 누릅니다 **확인**합니다. 자세한 내용은 [클라이언트 응용 프로그램](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)합니다.  
  
     합니다 **RelatedDataWalkthrough** 프로젝트에 추가한 생성 **솔루션 탐색기**합니다.  
  
## <a name="creating-the-data-source"></a>데이터 소스 만들기  
 이 단계에서는 Northwind 샘플 데이터베이스의 `Customers` 및 `Orders` 테이블을 기반으로 하는 데이터 집합을 만듭니다.  
  
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
  
8.  선택 합니다 **고객** 및 **주문** 테이블과 클릭 **마침**합니다.  
  
     합니다 **NorthwindDataSet** 프로젝트에 추가 됩니다 및 **고객** 테이블에 표시 됩니다는 **데이터 원본** 창입니다.  
  
## <a name="creating-controls-to-display-data-from-the-customers-table"></a>Customers 테이블의 데이터를 표시하는 컨트롤 만들기  
  
#### <a name="to-create-controls-to-display-the-customer-data-parent-records"></a>고객 데이터(부모 레코드)를 표시하는 컨트롤을 만들려면  
  
1.  에 **데이터 원본** 창에서 합니다 **고객** 테이블을 선택한 다음 드롭다운 화살표를 클릭 합니다.  
  
2.  선택할 **세부 정보** 합니다.  
  
3.  주를 끌어 **고객이** 에서 노드를 **데이터 원본** 창 맨 위에 **Form1**합니다.  
  
     설명 레이블이 있는 데이터 바인딩된 컨트롤이 레코드 탐색을 위한 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>와 함께 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)를 [CustomersTableAdapter](../data-tools/tableadapter-overview.md)를 <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
## <a name="creating-controls-to-display-data-from-the-orders-table"></a>Orders 테이블의 데이터를 표시하는 컨트롤 만들기  
 ![데이터 소스 창 관계를 보여 주는](../data-tools/media/datasources2.gif "DataSources2")  
  
#### <a name="to-create-controls-to-display-the-orders-for-each-customer-child-records"></a>각 고객의 주문(자식 레코드)을 표시하는 컨트롤을 만들려면  
  
-   에 **데이터 원본** 창 확장를 **고객** 노드의 마지막 열을 선택 하 고는 **고객** 테이블에 있는 확장명 가능한 **주문** 노드를 아래쪽으로 끌어 **Form1**합니다.  
  
     <xref:System.Windows.Forms.DataGridView>가 폼에 추가되고 새 <xref:System.Windows.Forms.BindingSource>(`OrdersBindingSource`) 및 TableAdapter(`OrdersTableAdapter`)가 구성 요소 트레이에 추가됩니다.  
  
    > [!NOTE]
    >  열기는 [속성 창](../ide/reference/properties-window.md) 선택 합니다 **OrdersBindingSource**합니다. <xref:System.Windows.Forms.BindingSource.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성을 검사하여 관련 레코드를 표시하기 위해 바인딩이 어떻게 구성되었는지 확인합니다. <xref:System.Windows.Forms.BindingSource.DataSource%2A>는 `CustomersBindingSource` 테이블이 아닌 <xref:System.Windows.Forms.BindingSource>(부모 테이블의 `Orders`)로 설정됩니다. <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성은 테이블 간의 관계를 설정하는 `FK_Orders_Customers` 개체의 이름인 <xref:System.Data.DataRelation>로 설정됩니다.  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
  
#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
2.  사용 하 여 다른 고객을 선택 합니다 **CustomersBindingNavigator** 올바른 주문이 표시 되는지 확인 하는 <xref:System.Windows.Forms.DataGridView>합니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램 요구 사항에 따라 마스터-세부 폼을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다. 이 연습에서 보완할 수 있는 한 가지 사항은 다음과 같습니다.  
  
-   `Customers` 테이블에 매개 변수화를 추가하여 `Customers` 레코드를 필터링합니다. 이렇게 하려면 데이터를 표시 하는 모든 컨트롤을 선택 합니다 `Customers` 테이블, 스마트 태그를 클릭 하 고, 선택 **쿼리 추가**합니다. 완료 합니다 [검색 조건 작성기 대화 상자](http://msdn.microsoft.com/library/0b306b92-f35e-45ef-a4be-3f653cd00c3d)합니다. 자세한 내용은 [방법: Windows Forms 응용 프로그램 매개 변수가 있는 쿼리를 추가](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: 관련 데이터에는 Windows Forms 응용 프로그램 표시](../data-tools/how-to-display-related-data-in-a-windows-forms-application.md)   
 [BindingSource 구성 요소 개요](http://msdn.microsoft.com/library/be838caf-fcb0-4b68-827f-58b2c04b747f)   
 [BindingNavigator 컨트롤 개요](http://msdn.microsoft.com/library/4423eede-f8d1-4d02-822f-5bf8432680d0)