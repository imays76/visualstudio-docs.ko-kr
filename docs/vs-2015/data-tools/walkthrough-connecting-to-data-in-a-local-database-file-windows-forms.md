---
title: '연습: 데이터에에서 연결 하는 로컬 데이터베이스 파일 (Windows Forms) | Microsoft Docs'
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
- databases, connecting to
- local data, SQL Express
- SQL Express, walkthroughs
- SQL Express, connecting
- data [Visual Studio], local
- data [Visual Studio], connecting to SQL Express
ms.assetid: 5e16b7da-3fdc-4e69-bdb4-e8e700481811
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 71898c88a8d7a1d4a119a7e7a932e295ae12eb34
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49176165"
---
# <a name="walkthrough-connecting-to-data-in-a-local-database-file-windows-forms"></a>연습: 로컬 데이터베이스 파일의 데이터에 연결(Windows Forms)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

데이터 집합을 만든 후 데이터 바인딩 컨트롤을 응용 프로그램에 추가하여 응용 프로그램의 로컬 데이터베이스 파일에서 데이터를 쉽고 빠르게 표시할 수 있습니다. 이 연습에 나와 있는 단계를 수행 하 여 만든 로컬 데이터베이스 파일의 데이터 표시 [디자이너를 사용 하 여 SQL 데이터베이스를 만들](../data-tools/create-a-sql-database-by-using-a-designer.md)합니다. Windows Forms 프로젝트를 만든 후에 해당 데이터베이스에 연결하고 고객 테이블의 데이터가 응용 프로그램을 위한 양식으로 데이터 그리드에 나타나도록 할지 지정합니다.  
  
 Visual Studio 2013에서 데이터베이스를 만들 때, SQL Server 2012의 데이터베이스 파일(.mdf)에 액세스하기 위해 SQL Server Express LocalDB 엔진을 사용합니다. 이전 버전의 Visual Studio에서는 SQL Server Express 엔진을 사용하여 데이터베이스 파일(.mdf)에 액세스합니다. 참조 [로컬 데이터 개요](../data-tools/local-data-overview.md)합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
 이 연습에는 다음 작업이 포함됩니다.  
  
-   [만들기 및 데이터 집합 구성](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md#BKMK_CreateDataset)  
  
-   [데이터 바인딩된 컨트롤 추가](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md#BKMK_AddCtrls)  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료 하려면 완료 하 여 만든 SampleDatabase.mdf 데이터베이스에 액세스 해야 [디자이너를 사용 하 여 SQL 데이터베이스를 만들](../data-tools/create-a-sql-database-by-using-a-designer.md)합니다.  
  
##  <a name="BKMK_CreateDataset"></a> 만들기 및 데이터 집합 구성  
  
#### <a name="to-create-and-configure-a-dataset"></a>데이터 집합을 만들고 구성하려면  
  
1.  Windows Forms 프로젝트를 만들고 이름을 **connectlocaldata로 지정**합니다.  
  
     참조 [클라이언트 응용 프로그램](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)합니다.  
  
2.  경우는 **데이터 원본** 창이 표시 되지 않는 Shift-Alt-D 키를 선택 하거나, 메뉴 모음에서 선택한 **보기**를 **기타 Windows**, **데이터소스표시**.  
  
3.  에 **데이터 원본** 창 선택 합니다 **새 데이터 소스 추가** 링크 합니다.  
  
     에 **데이터 소스 구성 마법사**, 선택는 **다음** 단추 두 번 기본 설정을 그대로 적용 합니다.  
  
4.  에 **데이터 연결 선택** 페이지를 선택 합니다 **새 연결** 단추입니다.  
  
     합니다 **데이터 소스 선택** 대화 상자가 나타납니다.  
  
5.  에 **데이터 원본** 목록에서 선택 **Microsoft SQL Server 데이터베이스 파일**를 선택한 후는 **계속** 단추입니다.  
  
     합니다 **연결 추가** 대화 상자가 나타납니다.  
  
6.  에 **데이터베이스 파일 이름** 상자를 완료 하 여 만든 파일을 지정 [디자이너를 사용 하 여 SQL 데이터베이스를 만들](../data-tools/create-a-sql-database-by-using-a-designer.md), 선택 또는 합니다 **찾아보기** 단추 찾은 후 해당 파일입니다.  
  
     기본적으로 사용자의 파일은\\*YourAccount*\Documents\Visual Studio *버전*\Projects\SampleDatabaseWalkthrough\SampleDatabaseWalkthrough 합니다.  
  
7.  아래 **서버에 로그온**, 기본값, 선택 합니다 **확인** 단추를 선택한 후는 **다음** 단추입니다.  
  
    > [!NOTE]
    >  로컬 데이터베이스 파일에 연결을 만들 때 프로젝트에 데이터베이스의 복사본을 만들 것인지 현재 위치에 있는 기존 데이터베이스 파일에 연결할 것인지 결정할 수 있습니다. 참조 [방법: 프로젝트의 로컬 데이터 파일 관리](../data-tools/how-to-manage-local-data-files-in-your-project.md)합니다.  
  
8.  나타나는 대화 상자에서 선택 **예** 프로젝트에 데이터베이스 파일을 복사 합니다.  
  
9. 에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지를 선택 합니다 **다음** 단추입니다.  
  
10. 에 **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 선택 합니다 **고객** 및 **주문** 확인란을 차례로 선택 된 **완료** 단추입니다.  
  
     합니다 **SampleDatabaseDataSet** 프로젝트에 추가 됩니다 및 **고객** 및 **주문** 테이블에 표시 합니다 **데이터 원본** 창.  
  
##  <a name="BKMK_AddCtrls"></a> 데이터 바인딩된 컨트롤 추가  
  
#### <a name="to-add-data-bound-controls"></a>데이터 바인딩된 컨트롤을 추가하려면  
  
1.  기본 이동 **고객** 에서 노드를 **데이터 원본** 창만 **Form1**합니다.  
  
     <xref:System.Windows.Forms.DataGridView>와 레코드 탐색에 사용되는 도구 스트립(<xref:System.Windows.Forms.BindingNavigator>)이 폼에 나타납니다. A [SampleDatabaseDataSet](../data-tools/dataset-tools-in-visual-studio.md)를 [CustomersTableAdapter](../data-tools/tableadapter-overview.md)를 <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
2.  응용 프로그램을 실행하고 이전 연습에서 추가한 데이터를 표시하려면 F5 키를 선택합니다.  
  
3.  노란색 추가 아이콘을 선택 (![Windows Form 추가 단추](../data-tools/media/addrecord.png "AddRecord")), 고객 레코드를 추가한 다음 디스크 아이콘을 선택 하 여 변경 내용을 저장 (![Windows형태로저장단추](../data-tools/media/saveinwf.png "SaveInWF")).  
  
4.  선택 하 고 다음 빨간색 삭제 아이콘을 선택 하 여 방금 만든 레코드를 삭제 (![Windows Form의 삭제 단추](../data-tools/media/deleterecord.png "DeleteRecord")).  
  
## <a name="next-steps"></a>다음 단계  
 데이터 원본을 열면 데이터 집합의 개체를 수정 하거나 만들 수 있습니다 합니다 [만들기 및 형식화 된 데이터 집합 편집](../data-tools/creating-and-editing-typed-datasets.md)합니다. 데이터 집합에 있는 데이터 테이블의 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트에도 유효성 검사 논리를 추가할 수 있습니다. 참조 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [로컬 데이터 개요](../data-tools/local-data-overview.md)   
 [방법: 프로젝트의 로컬 데이터 파일 관리](../data-tools/how-to-manage-local-data-files-in-your-project.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)