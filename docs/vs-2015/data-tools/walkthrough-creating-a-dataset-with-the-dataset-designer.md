---
title: '연습: 데이터 집합 디자이너를 사용 하 여 데이터 집합 만들기 | Microsoft Docs'
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
- datasets [Visual Basic], walkthroughs
- XML schemas, creating datasets
- data [Visual Studio], Dataset Designer
- Dataset Designer, walkthroughs
- datasets [Visual Basic], creating
ms.assetid: 12360f54-db6c-45d2-a91f-fee43214b555
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: d77d63cc82b7af6281183b3eae67d09b0454fffb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868263"
---
# <a name="walkthrough-creating-a-dataset-with-the-dataset-designer"></a>연습: 데이터 집합 디자이너를 사용하여 데이터 집합 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서 만들려는 사용 하 여 데이터 집합을 **데이터 집합 디자이너**합니다. 새 프로젝트를 만들고 새 추가 과정을 단계별로 걸립니다 **데이터 집합** 항목 되도록 합니다. 마법사를 사용 하지 않고 데이터베이스의 테이블을 기준으로 테이블을 만드는 방법에 배우게 됩니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
- 새로 만들 **Windows 응용 프로그램** 프로젝트입니다.  
  
- 추가 빈 **데이터 집합** 프로젝트 항목입니다.  
  
- 만들기 및 사용 하 여 데이터 집합을 작성 하 여 응용 프로그램에서 데이터 원본을 구성 합니다 **데이터 집합 디자이너**합니다.  
  
- Northwind 데이터베이스에 연결을 만드는 **서버 탐색기**합니다.  
  
- 데이터베이스의 테이블을 기반으로 데이터 집합에서 Tableadapter를 사용 하 여 테이블을 만듭니다.  
  
  [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스(SQL Server 또는 Access 버전) 액세스 권한. 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
## <a name="creating-a-new-windows-application-project"></a>새 Windows 응용 프로그램 프로젝트 만들기  
  
#### <a name="to-create-a-new-windows-application-project"></a>새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로그래밍 언어를 선택 합니다 **프로젝트 형식** 창입니다.  
  
3.  클릭 **Windows 응용 프로그램** 에 **템플릿** 창입니다.  
  
4.  프로젝트 이름을 `DatasetDesignerWalkthrough`를 클릭 하 고 **확인**합니다.  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로젝트를 추가 합니다 **솔루션 탐색기** 디자이너에서 새 양식을 표시 합니다.  
  
## <a name="adding-a-new-dataset-to-the-application"></a>응용 프로그램에 새 데이터 집합을 추가합니다.  
  
#### <a name="to-add-a-new-dataset-item-to-the-project"></a>프로젝트에 새 데이터 집합 항목을 추가 하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  에 **템플릿을** 상자를 **새 항목 추가** 대화 상자에서 클릭 **데이터 집합**합니다.  
  
3.  데이터 집합의 이름을 `NorthwindDataset`를 클릭 하 고 **추가**합니다.  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 라는 파일을 추가 합니다 **NorthwindDataset.xsd** 프로젝트를 만들고 합니다 **데이터 집합 디자이너**합니다.  
  
## <a name="creating-a-data-connection-in-server-explorer"></a>서버 탐색기에서 데이터 연결 만들기  
  
#### <a name="to-create-a-connection-to-the-northwind-database"></a>Northwind 데이터베이스에 대 한 연결을 만들려면  
  
1.  에 **뷰** 메뉴에서 클릭 **서버 탐색기**합니다.  
  
2.  **서버 탐색기**를 클릭 합니다 **데이터베이스에 연결** 단추입니다.  
  
3.  Northwind 샘플 데이터베이스에 대 한 연결을 만듭니다.  
  
    > [!NOTE]
    >  이 연습에서는 Northwind의 SQL Server 또는 Access 버전에 연결할 수 있습니다.  
  
## <a name="creating-the-tables-in-the-dataset"></a>데이터 집합에 테이블 만들기  
 이 섹션에서는 데이터 집합에 테이블을 추가 하는 방법을 설명 합니다.  
  
#### <a name="to-create-the-customers-table"></a>Customers 테이블을 만들려면  
  
1.  데이터 연결에서 만든 확장 **서버 탐색기**를 차례로 확장 합니다 **테이블** 노드.  
  
2.  끌어서 합니다 **고객** 에서 테이블 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
     A **고객이** 데이터 테이블 및 **CustomersTableAdapter** 데이터 집합에 추가 됩니다.  
  
#### <a name="to-create-the-orders-table"></a>Orders 테이블을 만들려면  
  
-   끌어서 합니다 **주문을** 에서 테이블 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
     **주문을** 데이터 테이블 **OrdersTableAdapter**, 및 간에 데이터 관계를 **고객** 및 **주문** 테이블에 추가 됩니다는 데이터 집합입니다.  
  
#### <a name="to-create-the-orderdetails-table"></a>OrderDetails 테이블을 만들려면  
  
-   끌어서 합니다 **Order Details** 에서 테이블 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
     **Order Details** 데이터 테이블 **순서 DetailsTableAdapter**, 간의 데이터 관계를 **주문** 및 **Order Details** 테이블 데이터 집합에 추가 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
  
### <a name="to-add-functionality-to-your-application"></a>응용 프로그램에 기능을 추가하려면  
  
-   데이터 집합을 저장 합니다.  
  
-   항목을 선택 합니다 **데이터 원본** 창 폼으로 끌어 합니다. 자세한 내용은 [Visual Studio에서 데이터 바인딩 Windows Forms 컨트롤](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)합니다.  
  
-   Tableadapter에 더 많은 쿼리를 추가 합니다. 자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)합니다.  
  
-   유효성 검사 논리를 추가 합니다 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 데이터 집합에 있는 데이터 테이블의 이벤트입니다. 자세한 내용은 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)