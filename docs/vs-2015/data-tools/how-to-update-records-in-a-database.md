---
title: '방법: 데이터베이스에서 레코드를 업데이트 합니다. | Microsoft Docs'
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
- records, updating
- data [Visual Studio], saving
- records, editing
- databases, updating
- TableAdapter.Update method
ms.assetid: cdc8a8e4-a5fa-40dd-9221-97b8571d802a
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: b880353b227eae86c7c35f274271fb404b62ede0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49199523"
---
# <a name="how-to-update-records-in-a-database"></a>방법: 데이터베이스에서 레코드 업데이트
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

사용할 수는 `TableAdapter.Update` 메서드를 데이터베이스에서 레코드 업데이트 (편집). `TableAdapter.Update` 메서드는 전달 된 매개 변수에 따라 다른 작업을 수행 하는 여러 오버 로드를 제공 합니다. 이러한 다양 한 메서드 시그니처를 호출한 결과 이해 하는 것이 반드시 합니다.  
  
> [!NOTE]
>  응용 프로그램에서 Tableadapter를 사용 하지 경우 명령 개체를 사용 하 여 데이터베이스에서 레코드를 업데이트할 수 있습니다 (예를 들어 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>). 명령 개체를 사용 하 여 데이터 업데이트에 대 한 자세한 내용은 아래 "명령 개체를 사용 하 여 레코드 업데이트"를 참조 하세요.  
  
 다음 표에서 다양 한 동작 `TableAdapter.Update` 메서드:  
  
|메서드|설명|  
|------------|-----------------|  
|`TableAdapter.Update(DataTable)`|모든 변경 내용을 저장 하려고 합니다 <xref:System.Data.DataTable> 데이터베이스에 있습니다. (예: 테이블에 삽입 된 행 추가 및 변경 된 테이블의 행 업데이트 테이블에서 삭제 된 행을 제거 합니다.)|  
|`TableAdapter.Update(DataSet)`|TableAdapter의 모든 변경 내용을 저장 하려면 TableAdapter 시도 연결 된 데이터 집합을 사용 하는 매개 변수를 하지만 <xref:System.Data.DataTable> 데이터베이스에 있습니다. (예: 테이블에 삽입 된 행 추가 및 변경 된 테이블의 행 업데이트 테이블에서 삭제 된 행을 제거 합니다.) **참고:** TableAdapter의 연결 된 <xref:System.Data.DataTable> 되는 <xref:System.Data.DataTable> TableAdapter 원래 구성 했을 때 생성 합니다.|  
|`TableAdapter.Update(DataRow)`|표시 된 변경 내용을 저장 하려고 <xref:System.Data.DataRow> 데이터베이스에 있습니다.|  
|`TableAdapter.Update(DataRows())`|배열의 모든 행의 변경 내용을 저장 하려고 <xref:System.Data.DataRow>데이터베이스에 있습니다.|  
|`TableAdapter.Update("new column values", "original column values")`|원래 열 값으로 식별 되는 단일 행의 변경 내용을 저장 하려고 합니다.|  
  
 일반적으로 사용 합니다 `TableAdapter.Update` 메서드를를 <xref:System.Data.DataSet>를 <xref:System.Data.DataTable>, 또는 <xref:System.Data.DataRow>응용 프로그램 데이터 집합을 사용 하 여 데이터를 저장 하는 경우 (s).  
  
 일반적으로 사용 하 여 `TableAdapter.Update` 응용 프로그램 개체를 사용 하 여 데이터를 저장 하는 경우 열 값을 사용 하는 메서드.  
  
 TableAdapter에 없는 경우는 `Update` 하거나 TableAdapter 저장된 프로시저를 사용 하도록 구성 되어 있는지를 의미 하는 다음 열 값을 사용 하는 메서드 또는 해당 `GenerateDBDirectMethods` 속성이 `false`합니다. TableAdapter의 설정 해 보십시오 `GenerateDBDirectMethods` 속성을 `true` 내에서 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md) 다음 TableAdapter를 다시 생성 하려면 데이터 집합을 저장 합니다. TableAdapter 아직 없는 경우는 `Update` 아마도 열 값을 다음 테이블을 사용 하는 메서드는 개별 행을 구분 하기 위해 충분 한 스키마 정보를 제공 하지 않습니다 (예를 들어, 기본 키에 설정 되어 테이블).  
  
## <a name="update-existing-records-using-tableadapters"></a>Tableadapter를 사용 하 여 기존 레코드를 업데이트 합니다.  
 Tableadapter에는 응용 프로그램의 요구 사항에 따라 데이터베이스에서 레코드를 업데이트 하는 다른 방법을 제공 합니다.  
  
 응용 프로그램 데이터 집합을 사용 하 여 데이터를 저장할 경우 단순히 원하는 레코드를 업데이트할 수 있습니다 <xref:System.Data.DataTable> 호출을 `TableAdapter.Update` 메서드와 전달을 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow>, 또는 배열을 <xref:System.Data.DataRow>s입니다. 위의 표에서 다양 한 `Update` 메서드.  
  
#### <a name="to-update-records-in-a-database-with-the-tableadapterupdate-method-that-takes-dataset-datatable-datarow-or-datarows"></a>DataSet, DataTable, DataRow, 또는 DataRows() 받아들이는 TableAdapter.Update 메서드를 사용 하 여 데이터베이스에서 레코드를 업데이트 하려면  
  
1.  원하는 레코드를 편집할 <xref:System.Data.DataTable> 직접 편집 하 여 합니다 <xref:System.Data.DataRow> 에 <xref:System.Data.DataTable>합니다. 자세한 내용은 [방법: DataTable에서 행 편집](http://msdn.microsoft.com/library/d5eea200-9bfa-4956-bf7c-08dd6fb6663c)합니다.  
  
2.  행을 편집한 후 합니다 <xref:System.Data.DataTable>를 호출 합니다 `TableAdapter.Update` 메서드. 전체에서 전달 하 여 업데이트 하는 데이터의 양을 제어할 수 있습니다 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 배열을 <xref:System.Data.DataRow>s, 단일 <xref:System.Data.DataRow>합니다.  
  
     다음 코드에서 레코드를 편집 하는 방법을 보여 줍니다는 <xref:System.Data.DataTable> 호출을 `TableAdapter.Update` 데이터베이스에 변경 내용을 저장 하는 방법입니다. (이 예제에서는 Northwind 데이터베이스 지역 테이블입니다.)  
  
     [!code-csharp[VbRaddataSaving#17](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form5.cs#17)]
     [!code-vb[VbRaddataSaving#17](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form5.vb#17)]  
  
 TableAdapter의 개체를 사용 하 여 응용 프로그램에 데이터를 저장 하는 응용 프로그램을 사용할 수 있습니다 `DBDirect` 개체에서 데이터를 데이터베이스에 직접 보내는 메서드. 이러한 메서드를 사용 하면 각 열에 대 한 개별 값 메서드 매개 변수로 전달할 수 있습니다. 이 메서드를 호출 메서드에 전달 된 열 값을 사용 하 여 데이터베이스에서 기존 레코드를 업데이트 합니다.  
  
 다음 절차에서는 Northwind `Region` 예를 들어 테이블입니다.  
  
#### <a name="to-update-records-in-a-database-using-the-tableadapterupdate-method-that-takes-column-values"></a>열 값을 받아들이는 TableAdapter.Update 메서드를 사용 하 여 데이터베이스에서 레코드를 업데이트 하려면  
  
-   TableAdapter의 호출 `Update` 메서드를 매개 변수로 각 열에 대 한 새 및 원래 값을 전달 합니다.  
  
    > [!NOTE]
    >  인스턴스에 사용할 수 없는 경우 사용 하려는 TableAdapter를 인스턴스화하십시오.  
  
     [!code-csharp[VbRaddataSaving#18](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#18)]
     [!code-vb[VbRaddataSaving#18](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#18)]  
  
## <a name="update-records-using-command-objects"></a>명령 개체를 사용 하 여 레코드를 업데이트 합니다.  
 다음 예에서는 명령 개체를 사용 하 여 데이터베이스에서 직접 기존 레코드를 업데이트 합니다. 명령 개체를 사용 하 여 명령 및 저장된 프로시저를 실행 하는 방법은 참조 하세요 [응용 프로그램에 데이터를 가져오는](../data-tools/fetching-data-into-your-application.md)합니다.  
  
 다음 절차에서는 Northwind `Region` 예를 들어 테이블입니다.  
  
#### <a name="to-update-existing-records-in-a-database-using-command-objects"></a>명령 개체를 사용 하 여 데이터베이스에서 기존 레코드를 업데이트 하려면  
  
-   새 명령 개체를 만들려면 설정 해당 `Connection`, `CommandType`, 및 `CommandText` 속성을 다음 연결을 열고 명령을 실행 합니다.  
  
     [!code-csharp[VbRaddataSaving#19](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#19)]
     [!code-vb[VbRaddataSaving#19](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#19)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 연결 하려는 데이터베이스 뿐만 아니라 원하는 테이블의 레코드를 업데이트할 수 있는 권한이 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: 데이터베이스에서 레코드를 삭제 합니다.](../data-tools/how-to-delete-records-in-a-database.md)   
 [데이터베이스에 새 레코드 삽입](../data-tools/insert-new-records-into-a-database.md)   
 [개체에서 데이터를 데이터베이스에 저장](../data-tools/save-data-from-an-object-to-a-database.md)   
 [Visual Studio에서 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)