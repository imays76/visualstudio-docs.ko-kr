---
title: TableAdapter 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vbData.Microsoft.VSDesigner.DataSource.DataAccessor
- vbdata.Microsoft.VSDesigner.DataSource.DataAccessor
- TableAdapter
- vs.data.TableAdapter
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], table adapters
- TableAdapters, queries
- data [Visual Studio], TableAdapters
- query data in Visual Studio
- TableAdapter.GetData
- TableAdapter.Fill
- data [Visual Studio], datasets
- TableAdapters
- table adapters
ms.assetid: a87c46a0-52ab-432a-a864-9ba55069f9eb
caps.latest.revision: 40
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: fb5ebcdaa1bebe67c2fb8e378c7345467dd10b78
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269050"
---
# <a name="tableadapter-overview"></a>TableAdapter 개요
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tableadapter는 데이터베이스에 연결, 쿼리 또는 저장된 프로시저를 실행 하 고, 반환된 된 데이터를 사용 하 여 해당 DataTable을 채울는 디자이너에서 생성 된 구성 요소입니다. Tableadapter는 데이터베이스에 다시 응용 프로그램에서 업데이트 된 데이터를 보내는 사용 됩니다. TableAdapter와 연결 된 테이블의 스키마를 따르는 데이터를 반환 하기만 TableAdapter에 원하는 만큼 많은 쿼리를 사용할 수 있습니다. 다음 다이어그램에서는 Tableadapter 데이터베이스와 메모리 내에서 기타 개체와 상호 작용 하는 방법을 보여 줍니다.  
  
 ![클라이언트 응용 프로그램에서 데이터 흐름](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")  
  
 사용 하 여 Tableadapter 설계 되어는 **데이터 집합 디자이너**, 생성 된 TableAdapter 클래스의 중첩 클래스로 생성 되지 않습니다는 <xref:System.Data.DataSet>합니다. 각 데이터 집합에 특정 별도 네임 스페이스에 있습니다. 예를 들어 라는 데이터 집합이 있다고 `NorthwindDataSet`와 연결 된 Tableadapter를 <xref:System.Data.DataTable>의 `NorthwindDataSet` 에 `NorthwindDataSetTableAdapters` 네임 스페이스. 특정 TableAdapter에 프로그래밍 방식으로 액세스 하려면 TableAdapter의 새 인스턴스를 선언 해야 합니다. 예를 들어:  
  
 [!code-csharp[VbRaddataTableAdapters#7](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Class1.cs#7)]
 [!code-vb[VbRaddataTableAdapters#7](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Class1.vb#7)]  
  
## <a name="associated-datatable-schema"></a>DataTable 스키마와 연결된  
 TableAdapter의 스키마를 정의 하려면 TableAdapter, 초기 쿼리 또는 저장된 프로시저 만들기가 사용 하는 경우의 연결 된 <xref:System.Data.DataTable>합니다. TableAdapter의를 호출 하 여이 초기 쿼리 또는 저장된 프로시저를 실행할 `Fill` 메서드 (연결 된 TableAdapter 채우는 <xref:System.Data.DataTable>). TableAdapter의 주 쿼리에 변경 관련된 데이터 테이블의 스키마에 반영 됩니다. 예를 들어, 기본 쿼리에서 열 제거 관련된 데이터 테이블의 열을 제거 합니다. TableAdapter에 대 한 추가 쿼리가 기본 쿼리에 포함 하지 않은 열을 반환 하는 SQL 문을 사용 하 여, 기본 쿼리와 쿼리 열 변경 내용을 동기화 하려면 디자이너 하려고 합니다. 자세한 내용은 [방법: Tableadapter 편집](http://msdn.microsoft.com/library/ca178745-e35a-45f1-a395-23cddfd8f855)합니다.  
  
## <a name="tableadapter-update-commands"></a>TableAdapter 업데이트 명령  
 TableAdapter의 업데이트 기능은 TableAdapter 마법사에 제공 된 기본 쿼리를 기반으로 얼마나 많은 정보를 사용할 수에 따라 달라 집니다. 예를 들어, 여러 테이블 (조인)의 값, 스칼라 값, 뷰 또는 집계 함수의 결과 인출 하도록 구성 된 Tableadapter 처음에 기본 데이터베이스로 업데이트를 보낼 수 있는 기능을 사용 하 여 만들어지지 않습니다. 그러나 INSERT, UPDATE 및 DELETE 명령에서 수동으로 구성할 수 있습니다 합니다 **속성** 창입니다.  
  
## <a name="tableadapter-queries"></a>TableAdapter 쿼리  
 ![여러 개의 쿼리가 있는 TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")  
  
 Tableadapter가 연결 된 데이터 테이블을 채우는 여러 쿼리를 포함할 수 있습니다. 해당 연결 된 데이터 테이블과 같은 스키마를 따르는 데이터를 반환 하는 각 쿼리도 응용 프로그램에 필요한 대로 TableAdapter에 대 한 많은 쿼리를 정의할 수 있습니다. 이 통해 서로 다른 조건에 맞는 데이터를 로드 합니다. 예를 들어 응용 프로그램이 고객의 테이블에 있으면 이름이 특정 문자로 시작 하는 모든 고객을 사용 하 여 테이블을 채우는 쿼리와 동일한 상태에 있는 모든 고객을 사용 하 여 테이블을 채우는 다른 쿼리를 만들 수 있습니다. 맞게를 `Customers` 만들면 지정된 된 상태에서 고객을 사용 하 여 테이블을 `FillByState` 상태 값에 대 한 매개 변수를 사용 하는 쿼리: `SELECT * FROM Customers WHERE State = @State`합니다. 호출 하 여 쿼리를 실행 합니다 `FillByState` 메서드 및 매개 변수 값 전달 같이: `CustomerTableAdapter.FillByState("WA")`합니다. 자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)합니다.  
  
 TableAdapter의 데이터 테이블과 동일한 스키마의 데이터를 반환 하는 쿼리 외에 스칼라 (단일) 값을 반환 하는 쿼리를 추가할 수 있습니다. 예를 들어, 고객의 수를 반환 하는 쿼리 만들기 (`SELECT Count(*) From Customers`)에 대 한 유효를 `CustomersTableAdapter` 반환 된 데이터 테이블의 스키마를 준수 하지 않는 경우에 합니다.  
  
## <a name="clearbeforefill-property"></a>ClearBeforeFill 속성  
 기본적으로 TableAdapter의 데이터 테이블 채우는 쿼리를 실행할 때마다 데이터를 지우고 쿼리의 결과만 테이블에 로드 됩니다. TableAdapter의 설정 `ClearBeforeFill` 속성을 `false` 를 추가 하 여 데이터 테이블의 기존 데이터에는 쿼리에서 반환 되는 데이터를 병합 하려는 경우. 데이터를 지우려면 여부에 관계 없이 필요한 명시적으로 업데이트를 데이터베이스로 다시 보내는 원하는 경우. 따라서 테이블을 채우는 다른 쿼리를 실행 하기 전에 테이블의 데이터에 대 한 변경 내용을 저장 해야 합니다. 자세한 내용은 [TableAdapter를 사용 하 여 데이터를 업데이트](../data-tools/update-data-by-using-a-tableadapter.md)합니다.  
  
## <a name="tableadapter-inheritance"></a>TableAdapter 상속  
 Tableadapter 구성 캡슐화 하 여 표준 데이터 어댑터의 기능을 확장 <xref:System.Data.Common.DataAdapter>합니다. 기본적으로 TableAdapter에서 상속 <xref:System.ComponentModel.Component> 캐스팅할 수 없는 및는 <xref:System.Data.Common.DataAdapter> 클래스입니다. TableAdapter를 캐스팅 하는 <xref:System.Data.Common.DataAdapter> 결과 <xref:System.InvalidCastException>합니다. TableAdapter의 기본 클래스를 변경 하려면에서 파생 된 클래스를 입력할 수 있습니다 <xref:System.ComponentModel.Component> 에 **기본 클래스** 에서 TableAdapter의 속성을 **데이터 집합 디자이너**합니다.  
  
## <a name="tableadapter-methods-and-properties"></a>TableAdapter 메서드 및 속성  
 TableAdapter 클래스가 아닌 부분을 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)],으로 조회할 수 없습니다이 문서의 및 또는 **개체 브라우저**합니다. 위에서 언급 한 마법사 중 하나를 사용 하면 디자인 타임에 생성 됩니다. TableAdapter를 만들 때 할당 된 이름은 사용 하는 테이블의 이름을 기반으로 합니다. 예를 들어 경우 TableAdapter 만들기 테이블을 기반으로 명명 된 데이터베이스의 `Orders`에서 TableAdapter 이름은 `OrdersTableAdapter`합니다. TableAdapter의 클래스 이름을 사용 하 여 변경할 수 있습니다 합니다 **이름을** 속성에는 **데이터 집합 디자이너**합니다.  
  
 다음은 일반적으로 사용 되는 메서드 및 Tableadapter의 속성입니다.  
  
|멤버|설명|  
|------------|-----------------|  
|`TableAdapter.Fill`|TableAdapter의 SELECT 명령의 결과 사용 하 여 TableAdapter의 연결 된 데이터 테이블을 채웁니다. 자세한 내용은 [방법: 데이터 집합을 데이터로 채우기](../data-tools/how-to-fill-a-dataset-with-data.md)합니다.|  
|`TableAdapter.Update`|변경 내용을 다시 데이터베이스에 보내고 업데이트의 영향을 받는 행 수를 나타내는 정수를 반환 합니다. 자세한 내용은 [TableAdapter를 사용 하 여 데이터를 업데이트](../data-tools/update-data-by-using-a-tableadapter.md)합니다.|  
|`TableAdapter.GetData`|반환 된 새 <xref:System.Data.DataTable> 데이터로 채워집니다.|  
|`TableAdapter.Insert`|데이터 테이블에 새 행을 만듭니다. 자세한 내용은 [방법: DataTable에 행 추가](http://msdn.microsoft.com/library/78ebbb43-c402-49cf-81da-0715289487bf)합니다.|  
|`TableAdapter.ClearBeforeFill`|데이터 테이블 중 하나를 호출 하기 전에 비어 있는지 여부를 결정 합니다 `Fill` 메서드.|  
  
## <a name="tableadapter-update-method"></a>TableAdapter 업데이트 메서드  
 Tableadapter에 대 한 읽기 및 쓰기 데이터베이스에서 데이터 명령을 사용 합니다. TableAdapter의 첫 `Fill` (main) 쿼리는 연결 된 데이터 테이블의 스키마를 만들기 위한 기초로 사용 뿐만 `InsertCommand`를 `UpdateCommand`, 및 `DeleteCommand` 연관 된 명령을 `TableAdapter.Update` 메서드. 즉, 호출 된 TableAdapter `Update` 메서드 때 생성 된 TableAdapter를 원래 구성한, 추가 쿼리 중 하나가 아닌 추가 사용 하 여 문을 실행 합니다 **TableAdapter쿼리구성마법사**.  
  
 TableAdapter를 사용 하면 효과적으로 일반적으로 수행 하는 명령 사용 하 여 동일한 작업을 수행 합니다. 예를 들어, 호출 하는 경우 어댑터 `Fill` 메서드를 어댑터에서 데이터 명령을 실행 합니다 해당 `SelectCommand` 속성 데이터 판독기를 사용 하 고 (예를 들어 <xref:System.Data.SqlClient.SqlDataReader>) 결과 집합을 데이터 테이블에 로드 합니다. 마찬가지로, 호출 하는 경우 어댑터의 `Update` 메서드를 적절 한 명령을 실행 (에 `UpdateCommand`를 `InsertCommand`, 및 `DeleteCommand` 속성) 각각에 대 한 데이터 테이블의 레코드를 변경 합니다.  
  
> [!NOTE]
>  기본 쿼리에서 충분 한 정보가 있는 경우는 `InsertCommand`, `UpdateCommand`, 및 `DeleteCommand` 명령을 TableAdapter를 생성할 때 기본적으로 생성 됩니다. TableAdapter의 주 쿼리는 단일 테이블 SELECT 문을 보다 많은 경우 디자이너는 생성할 수 있기를 `InsertCommand`, `UpdateCommand`, 및 `DeleteCommand`합니다. 이러한 명령은 생성 되지 않은 경우 오류가 발생할 수 있습니다를 실행할 때를 `TableAdapter.Update` 메서드.  
  
## <a name="tableadapter-generatedbdirectmethods"></a>TableAdapter GenerateDbDirectMethods  
 외에 `InsertCommand`, `UpdateCommand`, 및 `DeleteCommand`, Tableadapter는 데이터베이스에 대해 직접 실행할 수 있는 메서드를 사용 하 여 만들어집니다. 이러한 메서드 (`TableAdapter.Insert`, `TableAdapter.Update`, 및 `TableAdapter.Delete`) 데이터베이스의 데이터를 조작 하는 직접 호출할 수 있습니다. 즉, 삽입, 업데이트 및 보류 중인 삭제를 처리 하는 TableAdapter.Update를 호출 하는 대신 코드에서 이러한 개별 메서드를 호출할 수는 연결 된 데이터 테이블에 대 한 합니다.  
  
 이러한 직접 메서드를 만듭니다 하려면 TableAdapter의 설정 **GenerateDbDirectMethods** 속성을 `false` (에 **속성** 창). TableAdapter에 추가할 추가 쿼리는 독립 실행형-이러한 메서드를 생성 하지 않습니다.  
  
## <a name="tableadapter-support-for-nullable-types"></a>TableAdapter Nullable 형식 지원  
 TableAdapters를 nullable 형식 지원 `Nullable(Of T)` 고 `T?`입니다. Visual Basic의 nullable 형식에 대 한 자세한 내용은 참조 하세요. [Nullable 값 형식](http://msdn.microsoft.com/library/9ac3b602-6f96-4e6d-96f7-cd4e81c468a6)합니다. C#의 nullable 형식에 대 한 자세한 내용은 참조 하세요. [Nullable 형식 사용](http://msdn.microsoft.com/library/0bacbe72-ce15-4b14-83e1-9c14e6380c28)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [연습: 데이터에에서 연결 하는 데이터베이스 (Windows Forms)](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)