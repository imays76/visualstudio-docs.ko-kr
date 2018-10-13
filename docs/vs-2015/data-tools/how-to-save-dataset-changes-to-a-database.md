---
title: '방법: 데이터 집합 변경 내용을 데이터베이스에 저장 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DbDataAdapter.Update
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], saving
- databases, updating
- updating datasets, writing changes to data source
ms.assetid: c9970150-b71b-4c9d-a355-5efb6b510dca
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: a197952bcc392f84db3f612a158817237e077d36
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49202282"
---
# <a name="how-to-save-dataset-changes-to-a-database"></a>방법: 데이터베이스에 데이터 집합 변경 내용 저장
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

데이터 집합의 데이터를 수정 하 고 유효성을 검사 된 후 업데이트 된 데이터를 데이터베이스로 다시 보내는 원할 수 있습니다. 호출 하는 데이터베이스에 수정된 된 데이터를 보내려면 합니다 `Update` 메서드를 [TableAdapter](../data-tools/tableadapter-overview.md) 또는 데이터 어댑터입니다. 어댑터의 `Update` 메서드는 단일 데이터 테이블을 업데이트 하 고 올바른 명령을 (INSERT, UPDATE 또는 DELETE)에 따라 실행을 <xref:System.Data.DataRow.RowState%2A> 테이블의 각 데이터 행입니다.  
  
 관련된 테이블의 데이터를 저장 하는 경우 Visual Studio 데이터베이스에 정의 된 외래 키 제약 조건에 따라 적절 한 순서로 저장 작업을 지 원하는 TableAdapterManager 구성 요소를 제공 합니다. 자세한 내용은 [계층적 업데이트 개요](http://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)합니다.  
  
> [!NOTE]
>  데이터 집합의 콘텐츠를 사용 하 여 데이터 소스를 업데이트 하는 동안 오류가 발생할 수 있습니다, 되므로 어댑터를 호출 하는 코드에 넣어야 `Update` 메서드 내부에 `try` / `catch` 블록입니다.  
  
 데이터 소스를 업데이트 하는 정확한 절차를 비즈니스 요구 사항에 따라 다르지만 응용 프로그램에 다음 단계를 포함 해야 합니다.  
  
1.  내 데이터베이스에 업데이트를 보내는 코드를 실행 한 `try` / `catch` 블록입니다.  
  
2.  예외가 포착 되는 경우 오류를 발생 시키는 데이터 행을 찾습니다. 자세한 내용은 [방법: 행 해당가 오류를 찾습니다](http://msdn.microsoft.com/library/1fa907c5-fe66-4f29-a253-2b97b900050c)합니다.  
  
3.  데이터의 문제 (가능한 경우 프로그래밍 방식으로 또는 수정에 대 한 사용자에 게 잘못 된 행을 제공 하 여) 행을 한 다음 업데이트를 다시 시도 (<xref:System.Data.DataRow.HasErrors%2A> 속성인 <xref:System.Data.DataTable.GetErrors%2A> 메서드).  
  
## <a name="saving-data-to-a-database"></a>데이터베이스에 데이터 저장  
 호출 된 `Update` 메서드는 데이터 테이블의 이름을 전달 하는 TableAdapter 또는 데이터 어댑터의 데이터베이스에 쓸 값을 포함 합니다. 다시 데이터베이스에 단일 데이터 테이블에서 데이터를 저장 하는 방법은 참조 하세요 [연습: 데이터베이스 (단일 테이블)에 대 한 데이터 저장](http://msdn.microsoft.com/library/68befa96-7463-43e8-abcf-dc2f42ccd53d)합니다.  
  
#### <a name="to-update-a-database-with-a-dataset-using-a-tableadapter"></a>TableAdapter를 사용 하 여 데이터 집합을 사용 하 여 데이터베이스를 업데이트 하려면  
  
-   묶습니다 합니다 `TableAdapter.Update` 내에서 메서드를 `try` / `catch` 블록입니다. 다음 예제에서는의 콘텐츠를 사용 하 여 업데이트를 시도 하는 방법을 보여 줍니다 합니다 `Customers` 테이블에 `NorthwindDataSet`합니다.  
  
     [!code-csharp[VbRaddataSaving#9](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#9)]
     [!code-vb[VbRaddataSaving#9](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#9)]  
  
#### <a name="to-update-a-database-with-a-dataset-using-a-data-adapter"></a>데이터 어댑터를 사용 하 여 데이터 집합을 사용 하 여 데이터베이스를 업데이트 하려면  
  
-   묶습니다 합니다 `DataAdapter.Update` 내에서 메서드를 `try` / `catch` 블록입니다. 다음 예제에서는의 콘텐츠를 사용 하 여 데이터 원본에 대 한 업데이트를 시도 하는 방법을 보여 줍니다 `Table1` 에서 `DataSet1`합니다.  
  
     [!code-csharp[VbRaddataSaving#26](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#26)]
     [!code-vb[VbRaddataSaving#26](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#26)]  
  
## <a name="updating-two-related-tables-in-a-dataset"></a>데이터 집합에서 두 개의 관련된 테이블을 업데이트합니다.  
 데이터 집합의 관련된 테이블을 업데이트할 때 참조 무결성 제약 조건 위반 가능성을 줄이기 위해 적절 한 순서로 업데이트 해야 합니다. 명령 실행의 순서는 인덱스를 따릅니다도 <xref:System.Data.DataRowCollection> 데이터 집합의 합니다. 데이터 무결성 오류 발생을 방지 하려면 가장 좋은 방법은 다음 시퀀스에서 데이터베이스를 업데이트 하는:  
  
1.  자식 테이블: 레코드를 삭제 합니다.  
  
2.  부모 테이블: 삽입, 업데이트 및 레코드를 삭제 합니다.  
  
3.  자식 테이블: 레코드 삽입 및 업데이트 합니다.  
  
 여러 테이블에서 데이터 저장에 대 한 자세한 내용은 참조 하세요. [(여러 테이블) 데이터베이스에 데이터를 저장](../data-tools/save-data-to-a-database-multiple-tables.md)합니다.  
  
 둘 이상의 관련된 테이블을 업데이트 하는 경우 트랜잭션 내에서 모든 업데이트 논리를 포함 해야 합니다. 트랜잭션은 변경 내용을 커밋하기 전에 데이터베이스에 대한 모든 관련 변경 사항이 정상적으로 수행되었는지를 확인하는 프로세스입니다. 자세한 내용은 참조 하십시오 [트랜잭션 및 동시성](http://msdn.microsoft.com/library/f46570de-9e50-4fe6-8710-a8c31fa8569b)합니다.  
  
#### <a name="to-update-two-related-tables-using-a-tableadapter"></a>TableAdapter를 사용 하 여 두 개의 관련된 테이블을 업데이트 하려면  
  
1.  임시 역할을 세 <xref:System.Data.DataTable>서로 다른 레코드가 하도록 합니다.  
  
2.  호출 된 `Update` 내에서 행의 각 하위 집합에 대 한 메서드를 `try` / `catch` 블록. 업데이트 오류가 발생 하는 경우 제안 된 작업 과정 분기 및 해결할 것입니다.  
  
3.  데이터베이스의 데이터 집합에서 변경 내용을 커밋해야 합니다.  
  
4.  리소스를 해제 하도록 임시 데이터 테이블을 삭제 합니다.  
  
     [!code-csharp[VbRaddataSaving#27](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#27)]
     [!code-vb[VbRaddataSaving#27](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#27)]  
  
#### <a name="to-update-two-related-tables-using-a-data-adapter"></a>데이터 어댑터를 사용 하 여 두 개의 관련된 테이블을 업데이트 하려면  
  
-   호출 된 `Update` 각 데이터 어댑터의 메서드.  
  
     다음 예제에서는 관련된 테이블을 포함 하는 데이터 집합을 사용 하 여 데이터 소스를 업데이트 하는 방법을 보여 줍니다. 세 명의 임시 위의 시퀀스를 따르려면 <xref:System.Data.DataTable>s가 서로 다른 레코드가 만들어집니다. 그런 다음 `Update` 메서드 내에서 행의 각 하위 집합에 대 한 호출 될를 `try` / `catch` 블록입니다. 업데이트 오류가 발생 하는 경우 제안 된 작업 과정 분기 및 해결할 것입니다. 그런 다음 데이터 집합에 변경 내용을 커밋합니다. 마지막으로 리소스를 해제 하도록 임시 데이터 테이블을 삭제 합니다.  
  
     [!code-csharp[VbRaddataSaving#28](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#28)]
     [!code-vb[VbRaddataSaving#28](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#28)]  
  
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