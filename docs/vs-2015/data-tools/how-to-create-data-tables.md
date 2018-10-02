---
title: '방법: 데이터 테이블 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Microsoft.VSDesigner.DataSource.DesignTable
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], creating data tables
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
ms.assetid: 0e8bf4c4-3d05-4b20-9926-9d29914b26ed
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 596c2760e100bc45eefdde10743b3d9b45490b91
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555092"
---
# <a name="how-to-create-data-tables"></a>방법: 데이터 테이블 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

메모리에 데이터를 저장할 수 있습니다 <xref:System.Data.DataTable> 개체입니다. (데이터 집합으로 이루어져 있습니다 <xref:System.Data.DataTable> 개체입니다.) 일반적으로 사용 하 여 Tableadapter를 사용 하 여 새 데이터 테이블을 만듭니다는 [TableAdapter 구성 마법사](http://msdn.microsoft.com/library/3a373dd9-7b34-4d3c-a48b-69414512bac8) 에서 데이터베이스 개체를 끌어서 놓아 **서버 탐색기** 에 **데이터 집합 디자이너** .  
  
 새 Tableadapter를 만들 때 부산물로 데이터 테이블이 만들어집니다 합니다 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f) 도 만들 수 있지만 이러한도 하지 독립적으로 합니다. 드래그 하 여 독립 실행형 데이터 테이블을 만들면를 <xref:System.Data.DataTable> 에서 개체를 **데이터 집합** 탭을 **도구 상자** 에 **데이터 집합 디자이너**.  
  
> [!NOTE]
>  참조 데이터 테이블을 프로그래밍 방식으로 만들려면 [DataTable 만들기](http://msdn.microsoft.com/library/eecf9d78-60e3-4fdc-8de0-e56c13a89414)합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datatable-with-tableadapter"></a>TableAdapter를 사용 하 여 DataTable 만들기  
 Tableadapter 사용 하 여 데이터 테이블 데이터를 사용 하 여 테이블을 입력 하 고 데이터베이스에 변경 내용을 다시 작성 하는 메서드를 포함 합니다. 실행 하 여 Tableadapter를 만듭니다는 **TableAdapter 구성 마법사** 에서 데이터베이스 개체를 끌어서 놓아 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
#### <a name="to-create-a-new-data-table-with-tableadapter"></a>TableAdapter를 사용 하 여 새 데이터 테이블을 만들려면  
  
1.  데이터 집합을 엽니다는 **데이터 집합 디자이너**합니다. 정보를 참조 하세요 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)합니다.  
  
2.  끌어서를 **TableAdapter** 에서 **데이터 집합** 탭의 **도구 상자** 에 **데이터 집합 디자이너**.  
  
     합니다 **TableAdapter 구성 마법사** 열립니다.  
  
3.  마법사를 완료합니다. 자세한 내용은 참조 하세요. [TableAdapter 구성 마법사](http://msdn.microsoft.com/library/3a373dd9-7b34-4d3c-a48b-69414512bac8)  
  
#### <a name="to-create-a-new-data-table-with-a-tableadapter-from-server-explorer"></a>서버 탐색기에서 TableAdapter를 사용 하 여 새 데이터 테이블을 만들려면  
  
1.  데이터 집합을 엽니다는 **데이터 원본 디자이너**합니다.  
  
2.  데이터베이스 개체 (예를 들어, 테이블)에서 끌어 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
## <a name="creating-a-standalone-datatable"></a>독립 실행형 DataTable 만들기  
 독립 실행형 테이블 해야 `Fill` 논리가 구현 데이터로 채울 수 있습니다. 독립 실행형 데이터 테이블을 채우는 방법은 [DataAdapter에서 DataSet 채우기](http://msdn.microsoft.com/library/3fa0ac7d-e266-4954-bfac-3fbe2f913153)합니다.  
  
#### <a name="to-create-a-new-stand-alone-data-table"></a>새 독립 실행형 데이터 테이블을 만들려면  
  
1.  데이터 집합을 엽니다는 **데이터 집합 디자이너**합니다.  
  
2.  끌어서를 <xref:System.Data.DataTable> 에서 **데이터 집합** 탭의 **도구 상자** 에 **데이터 집합 디자이너**.  
  
3.  데이터 테이블을 정의 하는 열을 추가 합니다. 자세한 내용은 [방법: DataTable에 열 추가](http://msdn.microsoft.com/library/8ca21f77-b99a-47a7-a656-7cfd7a1bd9df)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataTable>   
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [형식화 된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)