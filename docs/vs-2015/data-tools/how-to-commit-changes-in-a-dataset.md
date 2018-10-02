---
title: '방법: 데이터 집합에서 변경 내용 커밋 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataSet.AcceptChanges
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- datasets [Visual Basic], committing changes
ms.assetid: 51931353-4d22-4e35-a9ef-6f2b44e1f7d9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 40acd2a706ef7bc00ea1f90e51e90705be5658c3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553361"
---
# <a name="how-to-commit-changes-in-a-dataset"></a>방법: 데이터 집합에서 변경 내용 커밋
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

레코드를 업데이트, 삽입, 삭제 하 여 데이터 집합에서 레코드를 변경할 때 데이터 집합은 레코드의 원래 버전과 현재 버전을 유지 합니다. 또한 각 행의 <xref:System.Data.DataRow.RowState%2A> 속성 레코드를 원래 상태로 있는 또는 업데이트, 삽입 되거나 삭제 여부를 추적 합니다. 이 정보 행의 특정 버전을 찾아야 할 때 유용 합니다. 일반적으로 다른 프로세스에 보낼 변경 된 모든 레코드의 하위 집합을 얻게 됩니다. 자세한 내용은 [방법: 변경 행 검색](http://msdn.microsoft.com/library/6ff0cbd0-5253-48e7-888a-144d56c2e0a9)합니다. 변경된 된 모든 행을 처리 한 후에 호출 하 여 변경 내용을 커밋할 수 있습니다 합니다 `AcceptChanges` 메서드를 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 또는 <xref:System.Data.DataRow>합니다. `AcceptChanges` 메서드는의 업데이트 메서드를 호출할 때 자동으로 호출 되는 [TableAdapter](../data-tools/tableadapter-overview.md) 또는 데이터 어댑터. 호출 `AcceptChanges` 후 변경 내용을 데이터베이스로 전송 합니다.  
  
 호출 하는 경우 <xref:System.Data.DataSet.AcceptChanges%2A> 에 <xref:System.Data.DataSet>모든 <xref:System.Data.DataRow> 아직 편집 모드에에서는 개체의 편집을 성공적으로 완료 합니다. 합니다 <xref:System.Data.DataRow.RowState%2A> 의 각 속성 <xref:System.Data.DataRow> 도 변경 됩니다. <xref:System.Data.DataRowState> 하 고 <xref:System.Data.DataRowState> 될 행 <xref:System.Data.DataRowState>, 및 <xref:System.Data.DataRowState> 행이 제거 됩니다.  
  
 경우는 <xref:System.Data.DataSet> 포함 <xref:System.Data.ForeignKeyConstraint> 개체를 호출 합니다 <xref:System.Data.DataSet.AcceptChanges%2A> 메서드를 <xref:System.Data.AcceptRejectRule> 적용할 합니다.  
  
### <a name="to-commit-changes-in-a-dataset"></a>데이터 집합의 변경 내용을 커밋하기 위해  
  
-   호출을 `AcceptChanges` 메서드를를 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 또는 <xref:System.Data.DataRow> 이러한 개체에 변경 내용을 커밋하기 위해.  
  
     다음 예제에서는 호출 하는 방법을 보여 줍니다 합니다 `AcceptChanges` 의 변경 내용을 커밋하는 메서드는 `Customers` 데이터 소스 업데이트 후 테이블:  
  
     [!code-csharp[VbRaddataEditing#11](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#11)]
     [!code-vb[VbRaddataEditing#11](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#11)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataSet.AcceptChanges%2A?displayProperty=fullName>   
 <xref:System.Data.DataTable.AcceptChanges%2A?displayProperty=fullName>   
 <xref:System.Data.DataRow.AcceptChanges%2A?displayProperty=fullName>   
 [데이터 저장](../data-tools/saving-data.md)   
 [방법: 변경 된 행을 검색](http://msdn.microsoft.com/library/6ff0cbd0-5253-48e7-888a-144d56c2e0a9)