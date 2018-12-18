---
title: '방법: DataRow의 특정 버전 가져오기 | Microsoft Docs'
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
- row states
- updating datasets, row states
- DataRow object
ms.assetid: d7cde25e-cef5-4559-b994-be00e258ac1f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 5bd8ae12c77c671e375043a0381a4b580d1a03d7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49255491"
---
# <a name="how-to-get-specific-versions-of-a-datarow"></a>방법: DataRow의 특정 버전 가져오기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

데이터 집합 유지 모두 원래 데이터 행을 변경 하는 경우 (<xref:System.Data.DataRowVersion>) 및 새 (<xref:System.Data.DataRowVersion>) 행의 버전입니다. 예를 들어를 호출 하기 전에 합니다 `AcceptChanges` 메서드를 응용 프로그램 레코드의 다른 버전에 액세스할 수 (에 정의 된 대로 <xref:System.Data.DataRowVersion> 열거형) 적절 하 게 변경 내용을 처리 하 고 합니다.  
  
> [!NOTE]
>  행의 서로 다른 버전을 편집한 후 및 하기 전에 해당 했습니다만 존재 합니다 `AcceptChanges` 메서드를 호출 합니다. 이후에 `AcceptChanges` 메서드를 호출한, 현재 및 원래 버전은 동일 합니다.  
  
 전달 된 <xref:System.Data.DataRowVersion> 값 열 인덱스 (또는 열의 이름 (문자열))과 함께 해당 열의 특정 행 버전 값을 반환 합니다. 변경된 된 열 중에 식별 되는 <xref:System.Data.DataTable.ColumnChanging> 고 <xref:System.Data.DataTable.ColumnChanged> 이벤트를 시점을 다른 검사는 행 버전 유효성 검사를 위해. 그러나 제약 조건을 일시적으로 일시 중단 하는 경우 해당 이벤트를 발생 하지 않습니다 있으며 프로그래밍 방식으로 변경 된 열을 식별 해야 합니다. 반복 하 여 이렇게 합니다 <xref:System.Data.DataTable.Columns%2A> 컬렉션과 다른 비교 <xref:System.Data.DataRowVersion> 값.  
  
## <a name="accessing-the-original-version-of-a-datarow"></a>DataRow의 원래 버전에 액세스  
  
#### <a name="to-get-the-original-version-of-a-record"></a>레코드의 원래 버전을 가져오려면  
  
-   에 전달 하 여 열의 값에 액세스 합니다 <xref:System.Data.DataRowVersion> 반환할 행의 합니다.  
  
     다음 예제에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Data.DataRowVersion> 의 원래 값을 검색할 값을 `CompanyName` 필드에 <xref:System.Data.DataRow>:  
  
     [!code-csharp[VbRaddataEditing#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#21)]
     [!code-vb[VbRaddataEditing#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#21)]  
  
## <a name="accessing-the-current-version-of-a-datarow"></a>DataRow의 현재 버전에 액세스  
  
#### <a name="to-get-the-current-version-of-a-record"></a>레코드의 현재 버전을 가져오려면  
  
-   열의 값에 액세스 하 고 반환 하려는 행의 버전을 나타내는 인덱스에는 매개 변수를 추가 합니다.  
  
     다음 예제에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Data.DataRowVersion> 의 현재 값을 검색할 값을 `CompanyName` 필드에 <xref:System.Data.DataRow>:  
  
     [!code-csharp[VbRaddataEditing#22](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#22)]
     [!code-vb[VbRaddataEditing#22](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#22)]  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)   
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)