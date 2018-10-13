---
title: '방법: 관련 데이터에는 Windows Forms 응용 프로그램 표시 | Microsoft Docs'
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
- Windows Forms, displaying data
- displaying data, related data
- related data, displaying
- displaying tables, related data
- data [Windows Forms], displaying
- displaying table data
- data [Windows Forms], related
- displaying data on forms, related data
- displaying table information
ms.assetid: 60b1f1ec-6257-42ab-83f0-06d54ed364fd
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 3fd7a29e1de66a5b5fd57dab1adbcf99128001ac
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49215464"
---
# <a name="how-to-display-related-data-in-a-windows-forms-application"></a>방법: Windows Forms 응용 프로그램에서 관련 데이터 표시
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

동일한 주 테이블 노드를 공유 하는 항목을 끌어 관련된 데이터를 표시할 수 있습니다 합니다 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) 폼입니다. 예를 들어 있는 데이터 소스가 있는 경우에 `Customers` 테이블과 관련 `Orders` 테이블에 두 테이블 (트리 뷰)에서 최상위 노드로 표시 합니다 **데이터 원본** 창. 확장을 `Customers` 노드 열을 표시 하 고 목록에서 마지막 열은 확장 가능한 노드는 표시 됩니다 있도록 나타내는 `Orders` 테이블. 이 노드는 고객에 대 한 관련된 주문을 나타냅니다. 이렇게 하면 고객을 선택 하 여 해당 고객의 주문 목록을 표시 하는 폼을 만들려는 경우이 단일 계층에서 표시 하려는 항목을 끌어는 것을 의미 합니다.  
  
 ![데이터 소스 창 관계를 보여 주는](../data-tools/media/datasources2.gif "DataSources2")  
관련된 레코드를 표시 하는 데이터 바인딩된 컨트롤 만들기  
  
 ![비디오 링크](../data-tools/media/playvideo.gif "PlayVideo") 이 항목의 비디오 버전을 참조 하세요. [How do i: Update Related Tables](http://go.microsoft.com/fwlink/?LinkId=143527)합니다.  
  
### <a name="to-create-controls-that-display-related-records"></a>관련된 레코드를 표시 하는 컨트롤을 만들려면  
  
1.  폼을 엽니다는 [Windows Forms 디자이너](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15)합니다.  
  
2.  엽니다는 **데이터 원본** 창입니다. 자세한 내용은 [방법: 데이터 소스 창 열기](../data-tools/how-to-open-the-data-sources-window.md)합니다.  
  
3.  관계에서 부모 테이블을 나타내는 노드를 확장 합니다. (부모 테이블에 일 대 다 관계의 "일" 쪽에 있는 테이블이입니다.)  
  
4.  관계의 부모 테이블에서 표시 하려는 모든 항목을 끌어 합니다 **데이터 원본** 창에서 폼으로 합니다.  
  
5.  관련 된 자식 테이블이 부모 테이블의 열 목록의 맨 아래에 있는 확장 가능한 노드로 나타납니다. 이러한 관련된 노드가 폼에서 표시 하려는 항목을 끌어 옵니다.  
  
    > [!NOTE]
    >  관련 되지 않은 별도 만듭니다 최상위 노드의 항목을 끌어 [BindingSource 구성 요소](http://msdn.microsoft.com/library/3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9) 관련된 레코드 탐색는 쉽게는 않습니다. 관련된 데이터를 바인딩할 같은 계층적 노드의에서 테이블을 선택 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [형식화 된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 탐색](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb)