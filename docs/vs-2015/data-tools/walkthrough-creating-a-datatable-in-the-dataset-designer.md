---
title: '연습: 데이터 집합 디자이너에서 DataTable 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
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
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
ms.assetid: abf0a2b5-e4e5-422e-97ef-55a0e35a82df
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 832dba200fca438d000bae101381389ea20cfb17
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550038"
---
# <a name="walkthrough-creating-a-datatable-in-the-dataset-designer"></a>연습: 데이터 집합 디자이너에서 DataTable 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습을 만드는 방법을 설명를 <xref:System.Data.DataTable> (TableAdapter) 없이 사용 하는 **데이터 집합 디자이너**. Tableadapter를 포함 하는 데이터 테이블을 만드는 방법에 대 한 정보를 참조 하세요 [만들기 및 Tableadapter 구성](../data-tools/create-and-configure-tableadapters.md)합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새 Windows 응용 프로그램 프로젝트 만들기  
  
-   응용 프로그램에 새 데이터 집합을 추가합니다.  
  
-   데이터 집합에 새 데이터 테이블을 추가합니다.  
  
-   데이터 테이블에 열 추가  
  
-   테이블에 대 한 기본 키 설정  
  
## <a name="creating-a-new-windows-application"></a>새 Windows 응용 프로그램 만들기  
  
#### <a name="to-create-a-new-windows-application-project"></a>새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로그래밍 언어를 선택 합니다 **프로젝트 형식** 창입니다.  
  
3.  클릭 **Windows 응용 프로그램** 에 **템플릿** 창입니다.  
  
4.  프로젝트 이름을 `DataTableWalkthrough`를 클릭 하 고 **확인**합니다.  
  
     Visual Studio 프로젝트를 추가 합니다 **솔루션 탐색기** 모습과 **Form1** 디자이너에서 합니다.  
  
## <a name="adding-a-new-dataset-to-the-application"></a>응용 프로그램에 새 데이터 집합을 추가합니다.  
  
#### <a name="to-add-a-new-dataset-item-to-the-project"></a>프로젝트에 새 데이터 집합 항목을 추가 하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
     새 항목 추가 대화 상자가 나타납니다.  
  
2.  에 **템플릿을** 상자에서 **데이터 집합**합니다.  
  
3.  **추가**를 클릭합니다.  
  
     Visual Studio 라는 파일을 추가 합니다 **DataSet1.xsd** 프로젝트를 만들고 합니다 **데이터 집합 디자이너**합니다.  
  
## <a name="adding-a-new-datatable-to-the-dataset"></a>데이터 집합에 새 DataTable 추가  
  
#### <a name="to-add-a-new-data-table-to-the-dataset"></a>데이터 집합에 새 데이터 테이블을 추가 하려면  
  
1.  끌어서를 **DataTable** 에서 **데이터 집합** 탭의 **도구 상자** 에 **데이터 집합 디자이너**.  
  
     라는 테이블 **DataTable1** 데이터 집합에 추가 됩니다.  
  
    > [!NOTE]
    >  TableAdapter를 포함 하는 데이터 테이블을 참조 하세요 [연습: 여러 개의 쿼리가 있는 TableAdapter 만들기](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)합니다.  
  
2.  제목 표시줄을 누릅니다 **DataTable1** 하 고 이름을 `Music`입니다.  
  
## <a name="adding-columns-to-the-data-table"></a>데이터 테이블에 열 추가  
  
#### <a name="to-add-columns-to-the-data-table"></a>데이터 테이블에 열을 추가 하려면  
  
1.  마우스 오른쪽 단추로 클릭 합니다 **음악** 테이블입니다. 가리킨 **추가**를 클릭 하 고 **열**합니다.  
  
2.  열 이름을 `SongID`입니다.  
  
3.  에 **속성** 창에서 설정 합니다 <xref:System.Data.DataColumn.DataType%2A> 속성을 <xref:System.Int16?displayProperty=fullName>합니다.  
  
4.  이 프로세스를 반복 하 고 다음 열을 추가 합니다.  
  
     `SongTitle`: <xref:System.String?displayProperty=fullName>  
  
     `Artist`: <xref:System.String?displayProperty=fullName>  
  
     `Genre`: <xref:System.String?displayProperty=fullName>  
  
## <a name="setting-the-primary-key-for-the-table"></a>테이블에 대 한 기본 키 설정  
 모든 데이터 테이블에 기본 키가 있어야 합니다. 기본 키 데이터 테이블의 특정 레코드를 고유 하 게 식별합니다.  
  
#### <a name="to-set-the-primary-key-of-the-data-table"></a>데이터 테이블의 기본 키를 설정 하려면  
  
-   마우스 오른쪽 단추로 클릭 합니다 **SongID** 열 및 클릭 **기본 키 설정**합니다.  
  
     키 아이콘 옆에 표시 되는 **SongID** 열입니다.  
  
## <a name="saving-your-project"></a>프로젝트를 저장합니다.  
  
#### <a name="to-save-the-datatablewalkthrough-project"></a>DataTableWalkthrough 프로젝트를 저장 하려면  
  
-   에 **파일** 메뉴에서 클릭 **모두 저장**합니다.  
  
## <a name="next-steps"></a>다음 단계  
 테이블을 만들었으므로 이제 다음 작업 중 하나를 수행 하는 것이 좋습니다.  
  
|대상|보기|  
|--------|---------|  
|데이터 입력 양식 만들기|[연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)합니다.|  
|테이블에 데이터 추가|[DataTable에 데이터 추가](http://msdn.microsoft.com/library/d6aa8474-7bde-48f7-949d-20dc38a1625b)합니다.|  
|테이블에서 데이터 보기|[DataTable에서 데이터를 보기](http://msdn.microsoft.com/library/1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc)합니다.|  
|데이터 편집|[DataTable 편집](http://msdn.microsoft.com/library/f08008a9-042e-4de9-94f3-4f0e502b1eb5)|  
|테이블에서 행을 삭제 합니다.|[DataRow 삭제](http://msdn.microsoft.com/library/c34f531d-4b9b-4071-b2d7-342c402aa586)|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)   
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)