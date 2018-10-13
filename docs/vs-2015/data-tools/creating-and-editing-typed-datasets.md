---
title: 만들기 및 형식화 된 데이터 집합 편집 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Designer_Microsoft.VSDesigner.DataSource.Designer.DataSourceRootDesigner
- vs.data.adddataset
dev_langs:
- VB
- CSharp
- C++
- aspx
- aspx
helpviewer_keywords:
- datasets [Visual Basic], visual designer
- data [Visual Studio], Dataset Designer
- Dataset Designer
ms.assetid: cd0dbe93-be9b-41e4-bc39-e9300678c1f2
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 8c18717cd2a5c7e05b79dbe575d919ef0c8670dd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49225844"
---
# <a name="creating-and-editing-typed-datasets"></a>형식화된 데이터 집합 만들기 및 편집
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

합니다**데이터 집합 디자이너** 는 형식화 된 데이터 집합 및 포함 된 개별 항목 만들기 / 편집 하는 데 사용할 수 있는 시각적 도구의 집합입니다.  
  
 합니다 **데이터 집합 디자이너** 형식화 된 데이터 집합에 포함 된 개체의 시각적 표현을 제공 합니다. 만들기 및 수정 [Tableadapter](../data-tools/tableadapter-overview.md), [TableAdapter 쿼리](../data-tools/how-to-create-tableadapter-queries.md), <xref:System.Data.DataTable>s <xref:System.Data.DataColumn>s, 및 <xref:System.Data.DataRelation>를 합니다 **데이터 집합 디자이너**합니다.  
  
 열려는 **데이터 집합 디자이너**에서 데이터 집합을 두 번 클릭 **솔루션 탐색기**의 데이터 집합을 마우스 오른쪽 단추로 클릭 합니다 **데이터 원본** 창과 클릭 **편집 데이터 집합 디자이너를 사용 하 여**입니다. 자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)합니다. 새 추가 <xref:System.Data.DataSet> 사용 하 여 항목을 **새 항목 추가** 대화 상자가 열립니다는 **데이터 집합 디자이너** 빈 데이터 집합 편집에 대 한 준비를 사용 하 여.  
  
> [!NOTE]
>  합니다 **데이터 집합 디자이너** 데이터 집합의 기능을 확장할 수 있습니다. 디자인 화면을 두 번 클릭 하거나 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기** 에 변경 되거나 삭제 되지 디자이너에서 데이터 집합으로 코드를 추가할 수 있는 partial 클래스 파일을 만듭니다. TableAdapter의 기능을 확장에 대 한 내용은 참조 하세요 [TableAdapter의 기능을 확장](../data-tools/extend-the-functionality-of-a-tableadapter.md)합니다.  
  
 다음 표에서 수행할 수 있는 일반적인 작업을 나열 합니다 **데이터 집합 디자이너**합니다.  
  
|대상|참조|  
|--------|---------|  
|TableAdapter 만들기|[TableAdapter 만들기 및 구성](../data-tools/create-and-configure-tableadapters.md)|  
|TableAdapter 편집|[방법: Tableadapter 편집](http://msdn.microsoft.com/library/ca178745-e35a-45f1-a395-23cddfd8f855)|  
|TableAdapter 쿼리 만들기|[방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)|  
|TableAdapter 쿼리 편집|[방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)|  
|만들기를 <xref:System.Data.DataTable>|[방법: 데이터 테이블 만들기](../data-tools/how-to-create-data-tables.md)|  
|편집을 <xref:System.Data.DataTable>|[DataTable 디자인](../data-tools/designing-datatables.md)|  
|만들기를 <xref:System.Data.DataColumn>|[방법: DataTable에 열 추가](http://msdn.microsoft.com/library/8ca21f77-b99a-47a7-a656-7cfd7a1bd9df)|  
|두 관계를 만들 <xref:System.Data.DataTable>s|[방법: 데이터 집합 디자이너를 사용 하 여 Datarelation 만들기](http://msdn.microsoft.com/library/a3ab4803-0b50-4b74-9920-ab20bfbf1aa2)|  
|데이터 집합의 기능을 확장|[방법: 데이터 집합의 기능을 확장](http://msdn.microsoft.com/library/dfbc21eb-7ea2-4942-addd-49677f5493be)|  
|데이터 테이블의 유효성 검사를 추가할 <xref:System.Data.DataTable.ColumnChanging> 이벤트|[방법: 열 변경 중 데이터 유효성 검사](http://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5)|  
|데이터 테이블의 유효성 검사를 추가할 <xref:System.Data.DataTable.RowChanging> 이벤트|[방법: 행 변경 중 데이터 유효성 검사](http://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc)|  
  
## <a name="creating-objects-on-the-design-surface"></a>디자인 화면에서 개체 만들기  
 추가 데이터 집합을 구성 하는 개별 개체를 편집 하 여 데이터 집합을 만들 수 있습니다. 다음 표에서 다양 한 개체에 대 한 설명은 합니다 **데이터 집합** 탭의 **도구 상자** 디자인 화면으로 끌어 올 수 있는:  
  
|Object|설명|  
|------------|-----------------|  
|TableAdapter|기본 데이터베이스와 통신 하 고 데이터 테이블을 채우는 데 사용 되는 데이터 연결 및 데이터 명령 컬렉션을 포함 합니다. 자세한 내용은 [TableAdapter 개요](../data-tools/tableadapter-overview.md) 하 고 [만들기 Tableadapter를 구성 하 고](../data-tools/create-and-configure-tableadapters.md)입니다.|  
|Query|TableAdapter 쿼리는 SQL 문과 저장된 프로시저를 실행 하는 강력한 형식의 메서드. TableAdapter 쿼리를 실행 데이터로 데이터 테이블 채우는 또는 다른 데이터베이스 작업을 수행 합니다. 자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)합니다. 빈 영역을 사용 하 여 쿼리를 끌어 반면 쿼리가 해당 테이블에 추가 테이블을 사용 하 여 쿼리를 끌어 합니다 **데이터 집합 디자이너** 전역 쿼리를 만듭니다. 자세한 내용은 [방법: TableAdapter에 전역 쿼리 추가](../data-tools/how-to-add-global-queries-to-a-tableadapter.md)합니다.|  
|<xref:System.Data.DataTable>|데이터베이스에서 반환 되는 행의 메모리 내 컬렉션을 나타냅니다.|  
|관계 (<xref:System.Data.DataRelation>)|두 부모-자식 관계를 나타내는 <xref:System.Data.DataTable>s입니다. 자세한 내용은 [DataRelation 개체 소개](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192) 하 고 [연습: 데이터 테이블 간의 관계를 만들](http://msdn.microsoft.com/library/9b3f1c87-7098-4ed4-a710-cde8f8059f82)합니다.|  
  
> [!NOTE]
>  합니다 **데이터 집합 디자이너** 기본 데이터베이스를 연결할 디자이너에는 데이터베이스의 후속 변경 내용은 자동으로 검색 하지 않으면 경우 데이터 집합에만 생성 됩니다. 기존.xsd를 새로 고치려면 다시 실행 합니다 **구성 마법사**합니다. 테이블 관계가 변경된 경우 관련 테이블을 제거하고 .xsd에 다시 추가합니다.  
  
## <a name="linq-to-dataset"></a>LINQ to Dataset  
 [!INCLUDE[linq_dataset](../includes/linq-dataset-md.md)] 사용 하도록 설정 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) 데이터에 대 한 <xref:System.Data.DataSet> 개체입니다. 자세한 내용은 [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 데이터 집합 디자이너를 사용 하 여 데이터 집합 만들기](../data-tools/walkthrough-creating-a-dataset-with-the-dataset-designer.md)   
 [연습: 여러 개의 쿼리가 있는 TableAdapter 만들기](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)   
 [연습: 데이터 집합 디자이너에서 DataTable 만들기](../data-tools/walkthrough-creating-a-datatable-in-the-dataset-designer.md)   
 [연습: 데이터 테이블 간에 관계 만들기](http://msdn.microsoft.com/library/9b3f1c87-7098-4ed4-a710-cde8f8059f82)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)