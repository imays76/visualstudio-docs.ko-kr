---
title: '방법: 데이터베이스에서 레코드를 삭제 합니다. | Microsoft Docs'
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
- data [Visual Studio], saving
- records, deleting
- TableAdapter.Delete method
- databases, deleting records
- deleting data
- TableAdapter.Update method
- saving data
ms.assetid: d74d2130-9732-4648-abea-241059c4a372
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 87ab5ccde2c1100fbd0efc5f4272efe27803b717
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49938619"
---
# <a name="how-to-delete-records-in-a-database"></a>방법: 데이터베이스에서 레코드 삭제
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

데이터베이스에서 레코드를 삭제 하려면 사용 합니다 `TableAdapter.Update` 메서드 또는 `TableAdapter.Delete` 메서드. 또는 응용 프로그램에서 Tableadapter를 사용 하는 경우 데이터베이스에서 레코드를 삭제 하려면 명령 개체를 사용할 수 있습니다 (예를 들어 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>).  
  
 합니다 `TableAdapter.Update` 반면 응용 프로그램 데이터를 저장할 데이터 집합을 사용 하는 경우에 일반적으로 메서드는는 `TableAdapter.Delete` 메서드는 응용 프로그램 개체를 사용 하 여 데이터를 저장 하는 경우에 일반적으로 사용 됩니다.  
  
 TableAdapter에 없는 경우는 `Delete` 메서드를 의미 하거나 TableAdapter 저장된 프로시저를 사용 하도록 구성 된 또는 해당 `GenerateDBDirectMethods` 속성이 `false`합니다. TableAdapter의 설정 해 보십시오 `GenerateDBDirectMethods` 속성을 `true` 내에서 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md) 다음 TableAdapter를 다시 생성 하려면 데이터 집합을 저장 합니다. TableAdapter 아직 없는 경우는 `Delete` 메서드를 다음 표를 제공 하지 않게 개별 행을 구분 하기 위해 충분 한 스키마 정보 (예를 들어, 기본 키에 설정 되어 테이블).  
  
## <a name="delete-records-using-tableadapters"></a>Tableadapter를 사용 하 여 레코드를 삭제 합니다.  
 Tableadapter에는 응용 프로그램의 요구 사항에 따라 데이터베이스에서 레코드를 삭제 하는 다른 방법을 제공 합니다.  
  
 응용 프로그램 데이터를 저장 하려면 데이터 집합을 사용 하는 경우 삭제할 수 있습니다 단순히 레코드에서 원하는 <xref:System.Data.DataTable> 에 <xref:System.Data.DataSet>, 다음 호출을 `TableAdapter.Update` 메서드. `TableAdapter.Update` 메서드 데이터 테이블의 변경 내용을 사용 하 고 해당 변경 내용 (삽입, 업데이트 및 삭제 된 레코드를 포함 하 여) 데이터베이스에 보냅니다.  
  
#### <a name="to-delete-records-from-a-database-using-the-tableadapterupdate-method"></a>TableAdapter.Update 메서드를 사용 하 여 데이터베이스에서 레코드를 삭제 하려면  
  
- 원하는에서 레코드를 삭제할 <xref:System.Data.DataTable> 삭제 하 여 <xref:System.Data.DataRow> 테이블의 개체입니다. 자세한 내용은 [방법: DataTable에서 행 삭제](http://msdn.microsoft.com/library/add481e5-08c7-4923-9276-f036ae29d31e)합니다. 행에서 삭제 된 후의 <xref:System.Data.DataTable>를 호출 합니다 `TableAdapter.Update` 메서드. 전체 전달 하 여 업데이트 하는 데이터의 양을 제어할 수 있습니다 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 배열을 <xref:System.Data.DataRow>s, 단일 <xref:System.Data.DataRow>합니다. 다음 코드에서 레코드를 삭제 하는 방법을 보여 줍니다는 <xref:System.Data.DataTable> 호출을 `TableAdapter.Update` 변경 내용을 전달 및 데이터베이스에서 행을 삭제 하는 메서드. (이 예제에서는 Northwind 데이터베이스의 `Region` 테이블입니다.)  
  
   [!code-csharp[VbRaddataSaving#20](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form5.cs#20)]
   [!code-vb[VbRaddataSaving#20](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form5.vb#20)]  
  
  개체를 사용 하 여 응용 프로그램에 데이터를 저장 하는 응용 프로그램을 데이터베이스에서 직접 데이터를 삭제 하려면 TableAdapter의 DBDirect 메서드를 사용할 수 있습니다. 호출 된 `Delete` 메서드는 전달 된 매개 변수 값을 기반으로 데이터베이스에서 레코드를 제거 합니다.  
  
#### <a name="to-delete-records-from-a-database-using-the-tableadapterdelete-method"></a>TableAdapter.Delete 메서드를 사용 하 여 데이터베이스에서 레코드를 삭제 하려면  
  
-   TableAdapter의 호출 `Delete` 의 매개 변수로 각 열에 대 한 값을 전달 하는 메서드를 `Delete` 메서드. (이 예제에서는 Northwind 데이터베이스의 `Region` 테이블입니다.)  
  
    > [!NOTE]
    >  인스턴스에 사용할 수 없는 경우 사용 하려는 TableAdapter를 인스턴스화하십시오.  
  
     [!code-csharp[VbRaddataSaving#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#21)]
     [!code-vb[VbRaddataSaving#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#21)]  
  
## <a name="delete-records-using-command-objects"></a>명령 개체를 사용 하 여 레코드를 삭제 합니다.  
 다음 예에서는 명령 개체를 사용 하 여 데이터베이스에서 직접 레코드를 삭제 합니다. 명령 개체를 사용 하 여 명령 및 저장된 프로시저를 실행 하는 방법은 참조 하세요 [응용 프로그램에 데이터를 가져오는](../data-tools/fetching-data-into-your-application.md)합니다.  
  
#### <a name="to-delete-records-from-a-database-using-command-objects"></a>명령 개체를 사용 하 여 데이터베이스에서 레코드를 삭제 하려면  
  
-   새 명령 개체를 만들고, 설정 해당 `Connection`하십시오 `CommandType`, 및 `CommandText` 속성. (이 예제에서는 Northwind 데이터베이스의 `Region` 테이블입니다.)  
  
     [!code-csharp[VbRaddataSaving#22](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#22)]
     [!code-vb[VbRaddataSaving#22](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#22)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 원하는 테이블에서 레코드를 삭제 하는 권한을 뿐만 아니라 연결 하려는 데이터베이스에 액세스할 수 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [데이터베이스에 새 레코드 삽입](../data-tools/insert-new-records-into-a-database.md)   
 [방법: 데이터베이스에서 레코드를 업데이트 합니다.](../data-tools/how-to-update-records-in-a-database.md)   
 [개체에서 데이터를 데이터베이스에 저장](../data-tools/save-data-from-an-object-to-a-database.md)   
 [Visual Studio에서 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)