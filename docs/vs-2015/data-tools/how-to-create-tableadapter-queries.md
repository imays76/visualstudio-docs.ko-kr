---
title: '방법: TableAdapter 쿼리 만들기 | Microsoft Docs'
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
- TableAdapters, creating queries
- queries [Visual Studio], creating
- data [Visual Studio], TableAdapter queries
- queries [Visual Studio], TableAdapters
ms.assetid: df0cf4a5-e9cc-4de6-8b94-ce74fb7b2452
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: c4b800bcb70e41e1d80bf9a0a37d72f08f78c7a6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49195548"
---
# <a name="how-to-create-tableadapter-queries"></a>방법: TableAdapter 쿼리 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

TableAdapter 쿼리는 SQL 문 또는 응용 프로그램 데이터베이스에 대해 실행할 수 있는 저장된 프로시저입니다.  
  
 응용 프로그램에 필요한 만큼의 쿼리는 TableAdapter에 추가 합니다. TableAdapter 쿼리는 TableAdapter의 메서드로 표시 됩니다. 호출 하는 쿼리를 만들 때 `FillByCity` city 값을 나타내는 매개 변수를 사용 하는 쿼리는 TableAdapter에 추가 됩니다. 올바른 유형의 매개 변수를 인수로 사용 하는 형식화 된 메서드가으로 추가 됩니다-이 경우 city 값을 나타내는 문자열입니다. 모든 개체에 메서드와 마찬가지로 TableAdapter 쿼리를 호출합니다. 예를 들어, 다음 코드를 실행 합니다 `FillByCity` 쿼리 및 채우기 합니다 `Customers` 도시 값을 사용 하 여 모든 고객을 사용 하 여 테이블 `Seattle`:  
  
 [!code-csharp[VbRaddataTableAdapters#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Form1.cs#1)]
 [!code-vb[VbRaddataTableAdapters#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Form1.vb#1)]  
  
 TableAdapter 쿼리는 데이터 테이블을 채울 수 있습니다 (`Fill` 하 고 `FillBy` 쿼리) 쿼리에서 반환 된 데이터로 채워진 새 데이터 테이블을 반환 하거나 (`GetData` 및 `GetDataBy` 쿼리).  
  
 쿼리를 실행 하 여 기존 Tableadapter에 추가할 수 있습니다 합니다 [Tableadapter 편집](../data-tools/editing-tableadapters.md)합니다. (모든 TableAdapter를 마우스 오른쪽 단추로 클릭 하 고 선택 **쿼리 추가**.)  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="create-a-query-in-the-dataset-designer"></a>데이터 집합 디자이너에서 쿼리 만들기  
  
#### <a name="to-add-a-query-to-a-tableadapter-in-the-dataset-designer"></a>데이터 집합 디자이너의 TableAdapter에 쿼리를 추가 하려면  
  
1.  데이터 집합을 엽니다는 **데이터 집합 디자이너**합니다. 자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)합니다.  
  
2.  원하는 TableAdapter를 마우스 오른쪽 단추로 클릭 **쿼리 추가**합니다.  
  
     또는  
  
3.  끌어서를 **쿼리** 에서 **데이터 집합** 탭의 **도구 상자** 디자이너에서 테이블을 합니다.  
  
     합니다 **TableAdapter 쿼리 구성 마법사** 열립니다.  
  
4.  마법사를 완료 합니다. 쿼리는 TableAdapter에 추가 됩니다.  
  
## <a name="create-a-query-directly-on-a-form-in-your-windows-application"></a>Windows 응용 프로그램의 폼에 직접 쿼리 만들기  
 TableAdapter의 인스턴스를 폼에 사용 하 여 쿼리를 추가할 수 있습니다 합니다 [검색 조건 작성기 대화 상자](http://msdn.microsoft.com/library/0b306b92-f35e-45ef-a4be-3f653cd00c3d)를 추가 하는 <xref:System.Windows.Forms.ToolStrip> 입력 쿼리를 여는 데 필요한 매개 변수를 허용 하는 폼에 컨트롤 뿐만 쿼리를 실행 하는 단추입니다.  
  
#### <a name="to-add-a-query-to-a-tableadapter-using-the-search-criteria-dialog-box"></a>검색 조건 대화 상자를 사용 하 여 TableAdapter에 쿼리를 추가 하려면  
  
1.  구성 요소 트레이에 TableAdapter를 선택 합니다.  
  
2.  TableAdapter의 스마트 태그를 클릭 하 고 선택 **쿼리 추가**합니다.  
  
3.  대화 상자를 완료 하 고 쿼리가 TableAdapter에 추가 됩니다. 자세한 내용은 [검색 조건 작성기 대화 상자](http://msdn.microsoft.com/library/0b306b92-f35e-45ef-a4be-3f653cd00c3d)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)   
 [형식화 된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [방법: Windows Forms BindingNavigator 컨트롤을 사용 하 여 데이터를 이동 합니다.](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [연습: 여러 개의 쿼리가 있는 TableAdapter 만들기](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)