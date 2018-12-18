---
title: '방법: 데이터 집합을 데이터로 채우기 | Microsoft Docs'
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
- TableAdapter.GetData
- TableAdapter.Fill
- datasets [Visual Basic], filling
- DataTable objects, loading
- data [Visual Basic], loading into datasets
ms.assetid: 7ab436d4-54ba-4621-902f-3f193279e18c
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: f36aa2dac656f6fd27b656d0ddfb58a758eb6487
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49295999"
---
# <a name="how-to-fill-a-dataset-with-data"></a>방법: 데이터 집합을 데이터로 채우기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

개인 데이터를 로드 하는 것을 가리킵니다 "데이터를 사용 하 여 데이터 집합을 채우는" 구 <xref:System.Data.DataTable> 데이터 집합을 구성 하는 개체입니다. TableAdapter 쿼리를 실행 하 여 또는 데이터 어댑터를 실행 하 여 데이터 테이블을 채울 있습니다 (예를 들어 <xref:System.Data.SqlClient.SqlDataAdapter>) 명령입니다.  
  
 Tableadapter 또는 데이터 어댑터를 사용 해야 하는지 여부는 데이터 집합을 만드는 방법에 따라 달라 집니다. 디자인 도구를 사용 하는 경우 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]와 같은 합니다 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f), 데이터 집합에 Tableadapter. Tableadapter에 대 한 자세한 내용은 참조 하세요. [TableAdapter 개요](../data-tools/tableadapter-overview.md)합니다. 프로그래밍 방식으로 데이터 집합을 만든 경우 일반적으로 데이터 테이블에 데이터를 로드 하려면 데이터 어댑터 만들기 해야 합니다.  
  
> [!NOTE]
>  항목을 끌어서 놓으면 합니다 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) 폼으로 데이터를 사용 하 여 데이터 테이블을 채우는 코드를 자동으로 추가 됩니다는 `Form_Load` 이벤트 처리기입니다. 특정 테이블에 맞게 정확한 구문을 보려면 코드 편집기에서 폼을 엽니다. 폼을 로드할 때 테이블을 입력 하려면이 코드를 일부 다른 메서드를 이동 하거나 완전히 제거 수 있습니다.  
  
## <a name="filling-a-dataset-using-a-tableadapter"></a>TableAdapter를 사용 하 여 데이터 집합 채우기  
 데이터 집합의 데이터 테이블에 데이터를 로드 하려면 TableAdapter에 쿼리를 호출할 수 있습니다. 전달 된 <xref:System.Data.DataTable> TableAdapter 쿼리를 채우려는 경우. 쿼리에서 매개 변수를 사용 하는 경우는 메서드에 전달 합니다. 데이터 집합을 여러 테이블이 포함 된 경우 각 테이블에 대 한 별도 Tableadapter에 있어야 하 고 따라서 각 테이블 개별적으로 채워야 합니다.  
  
> [!NOTE]
>  기본적으로는 TableAdapter 쿼리를 실행할 때마다 결과 테이블에 로드 되 고 쿼리 하기 전에 테이블의 데이터 해제 됩니다. 테이블의 기존 데이터를 보관 하 고 TableAdapter의을 설정 하 여 결과 추가 `ClearBeforeFill` 속성을 `false`입니다.  
  
#### <a name="to-fill-a-dataset-with-data-using-a-tableadapter"></a>TableAdapter를 사용 하 여 데이터를 사용 하 여 데이터 집합에 맞게  
  
1.  폼 이나 구성 요소를 엽니다는 **코드 편집기**합니다.  
  
2.  어디서 나 데이터를 사용 하 여 데이터 테이블을 로드 해야 하는 응용 프로그램에서 코드를 추가 합니다. 쿼리 매개 변수를 사용 하지 않는, 경우에 전달 된 <xref:System.Data.DataTable> 채우려는 경우. 코드는 다음과 같아야 합니다.  
  
     [!code-csharp[VbRaddataFillingAndExecuting#4](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#4)]
     [!code-vb[VbRaddataFillingAndExecuting#4](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#4)]  
  
3.  쿼리에서 매개 변수를 사용 하는 경우 전달 된 <xref:System.Data.DataTable> 채우기 및 쿼리에서 예상 매개 변수를 합니다. 쿼리에서 실제 매개 변수에 따라 코드를 다음 예제와 비슷하게 표시:  
  
     [!code-csharp[VbRaddataFillingAndExecuting#5](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#5)]
     [!code-vb[VbRaddataFillingAndExecuting#5](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#5)]  
  
## <a name="filling-a-dataset-using-a-dataadapter"></a>DataAdapter를 사용 하 여 데이터 집합 채우기  
 데이터 어댑터를 호출 하면 `Fill` 메서드. 이렇게 하면 SQL 문을 실행 하는 어댑터 또는 저장된 프로시저에서 참조 된 해당 `SelectCommand` 속성 데이터 집합의 테이블에 결과 넣습니다. 데이터 집합을 여러 테이블이 포함 된 경우 각 테이블에 대 한 별도 데이터 어댑터가 있어야 하 고 따라서 각 테이블 개별적으로 채워야 합니다.  
  
#### <a name="to-fill-a-dataset-with-data-using-a-dataadapter"></a>DataAdapter를 사용 하 여 데이터를 사용 하 여 데이터 집합에 맞게  
  
-   호출을 <xref:System.Data.Common.DataAdapter.Fill%2A> 메서드를 <xref:System.Data.Common.DataAdapter>전달를 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable> 데이터를 로드 하. 예를 들어:  
  
     [!code-csharp[VbRaddataFillingAndExecuting#6](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#6)]
     [!code-vb[VbRaddataFillingAndExecuting#6](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#6)]  
  
     일반적으로 이름을 제공 해야 합니다 <xref:System.Data.DataTable> 데이터를 로드 하 합니다. 이름을 전달 하는 경우는 <xref:System.Data.DataSet> 특정 데이터 테이블 대신를 <xref:System.Data.DataTable> 라는 `Table1` 데이터 집합에 추가 되 고 데이터베이스에서 결과 사용 하 여 로드 (기존 데이터를 로드 하는 대신 <xref:System.Data.DataTable> 데이터 집합에서). 자세한 내용은 [DataAdapter에서 DataSet 채우기](http://msdn.microsoft.com/library/3fa0ac7d-e266-4954-bfac-3fbe2f913153)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Tableadapter를 사용 하 여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)