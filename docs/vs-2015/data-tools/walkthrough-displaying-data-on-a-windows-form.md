---
title: '연습: Windows Form에 데이터 표시 | Microsoft Docs'
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
- displaying data on forms, walkthroughs
- Windows Forms, displaying data
- Windows applications, displaying data
- data binding, Windows Forms
- data [Visual Studio], displaying on Windows Forms
- forms, displaying data
ms.assetid: f6e08c2c-c792-43de-adf3-3e52c0100225
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 3decf0da6dd6d16c0128fdaeedf2fcd0cea94871
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555108"
---
# <a name="walkthrough-displaying-data-on-a-windows-form"></a>연습: Windows Form에 데이터 표시
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

응용 프로그램 개발에서 가장 일반적인 시나리오 중 하나는 Windows 기반 응용 프로그램의 폼에 데이터를 표시하는 것입니다. 항목을 끌어 폼에 데이터를 표시할 수 있습니다 합니다 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) 폼입니다. 이 연습에서는 여러 개별 컨트롤에서 단일 테이블의 데이터를 표시하는 단순 폼을 만듭니다. 이 예에서는 Northwind 샘플 데이터베이스의 `Customers` 테이블을 사용합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새로 만들 **Windows 응용 프로그램** 프로젝트입니다.  
  
-   만들기 및 사용 하 여 데이터 집합을 구성 합니다 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)합니다.  
  
-   항목을 끌어오는 경우 폼에 만들어질 컨트롤을 선택 하 여 **데이터 원본** 창입니다. 자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
-   항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다는 **데이터 원본** 창에서 폼으로 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스. 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
## <a name="creating-the-windows-application"></a>Windows 응용 프로그램 만들기  
 첫 번째 단계를 만드는 것을 **Windows 응용 프로그램** 프로젝트입니다.  
  
#### <a name="to-create-the-new-windows-application-project"></a>새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로젝트 이름을 `DisplayingDataonaWindowsForm`로 지정합니다.  
  
3.  선택 **Windows 응용 프로그램** 누릅니다 **확인**합니다. 자세한 내용은 [클라이언트 응용 프로그램](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)합니다.  
  
     합니다 **DisplayingDataonaWindowsForm** 프로젝트에 추가한 생성 **솔루션 탐색기**합니다.  
  
## <a name="creating-the-data-source"></a>데이터 소스 만들기  
 이 단계에서는 사용 하 여 데이터 소스를 만듭니다는 **데이터 소스 구성 마법사** 기반을 `Customers` Northwind 샘플 데이터베이스의 테이블입니다. 연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다. Northwind 샘플 데이터베이스 설정에 대 한 내용은 참조 하세요 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
#### <a name="to-create-the-data-source"></a>데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  에 **데이터 원본** 창에서 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스** 를 선택하고 **다음**을 클릭합니다.  
  
4.  에 **데이터 연결 선택** 페이지 중 하나를 수행 합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   선택 **새 연결** 시작 하는 **연결 추가/수정** 대화 상자...  
  
5.  데이터베이스에서 암호를 요구 하는 경우 중요 한 데이터를 포함 한 다음 클릭 옵션을 선택 **다음**합니다.  
  
6.  클릭 **다음** 에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지입니다.  
  
7.  확장 된 **테이블** 노드에서 **데이터베이스 개체 선택** 페이지입니다.  
  
8.  선택 된 **고객** 테이블을 마우스 클릭 **마침**합니다.  
  
     합니다 **NorthwindDataSet** 프로젝트에 추가 됩니다 및 **고객** 테이블에 표시 됩니다는 **데이터 원본** 창입니다.  
  
## <a name="setting-the-controls-to-be-created"></a>만들 컨트롤 설정  
 이 연습에 대 한 데이터의 수를 **세부 정보** 레이아웃 데이터를 개별 컨트롤에에서 표시 되는 위치입니다. (대안 기본값인 **그리드** 레이아웃에 데이터 표시 되는 위치를 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.)  
  
#### <a name="to-set-the-drop-type-for-the-items-in-the-data-sources-window"></a>데이터 소스 창에서 항목에 대한 삭제 유형을 설정하려면  
  
1.  확장 된 **고객** 에서 노드를 **데이터 원본** 창.  
  
2.  놓기 형식을 변경 합니다 **고객** 테이블 **세부 정보** 를 선택 하 여 **세부 정보** 드롭 다운 목록에서를 **고객** 노드. 자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
3.  변경 된 **CustomerID** 열의 드롭 유형을 선택 하 여 레이블 **레이블** 컨트롤 목록에서를 **CustomerID** 노드.  
  
## <a name="creating-the-form"></a>폼 만들기  
 항목을 끌어 데이터 바인딩된 컨트롤을 만들 합니다 **데이터 원본** 창에서 폼으로 합니다.  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>폼에서 데이터 바인딩된 컨트롤을 만들려면  
  
-   주를 끌어 **고객** 에서 노드를 **데이터 원본** 창에서 폼입니다.  
  
     설명 레이블이 있는 데이터 바인딩된 컨트롤이 레코드 탐색을 위한 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>와 함께 폼에 나타납니다. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)를 [CustomersTableAdapter](../data-tools/tableadapter-overview.md)를 <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
  
#### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면  
  
-   F5 키를 누릅니다.  
  
-   <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 사용하여 레코드를 탐색합니다.  
  
## <a name="next-steps"></a>다음 단계  
 응용 프로그램 요구 사항에 따라 데이터 바인딩된 Windows Form을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다. 이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
-   폼에 검색 기능을 추가합니다. 자세한 내용은 [방법: Windows Forms 응용 프로그램 매개 변수가 있는 쿼리를 추가](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)합니다.  
  
-   업데이트를 데이터베이스로 다시 보내는 기능을 추가합니다. 자세한 내용은 [연습: 데이터베이스 (단일 테이블)에 대 한 데이터 저장](http://msdn.microsoft.com/library/68befa96-7463-43e8-abcf-dc2f42ccd53d)합니다.  
  
-   추가 합니다 `Orders` 테이블을 선택 하 여 데이터 집합 **마법사를 사용 하 여 데이터 집합 구성** 내에서 **데이터 원본** 창. 끌어 관련된 데이터를 표시 하는 컨트롤을 추가할 수 있습니다는 **주문** 노드 (아래를 **팩스** 내에 있는 열의 **고객** 테이블) 폼입니다. 자세한 내용은 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../data-tools/how-to-display-related-data-in-a-windows-forms-application.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)