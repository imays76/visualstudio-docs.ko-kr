---
title: '방법: TableAdapter에 전역 쿼리 추가 | Microsoft Docs'
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
- global functions, datasets
- scalar functions, datasets
- TableAdapters, global queries
- data [Visual Studio], TableAdapters
- datasets [Visual Basic], scalar functions
- TableAdapter Query Configuration Wizard
- datasets [Visual Basic], global functions
- TableAdapter queries
- queries [Visual Studio], TableAdapters
ms.assetid: 4abffd6b-2e9f-4ef3-99b2-6e9ae4ad4679
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 681fea494557e555c745d33c07c4e2c25cfe0f88
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549907"
---
# <a name="how-to-add-global-queries-to-a-tableadapter"></a>방법: TableAdapter에 전역 쿼리 추가
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*전역 쿼리* 는 단일 (스칼라) 값 또는 값을 반환 하는 SQL 쿼리입니다. 일반적으로 전역 함수는 삽입, 업데이트, 삭제 및 테이블 또는 특정 순서로 모든 항목에 대 한 총 요금은 고객의 수를 반환 하는 등의 정보를 집계 하는 등의 데이터베이스 작업을 수행 합니다.  
  
 전역 쿼리를 실행 하 여 추가 합니다 **TableAdapter 쿼리 구성 마법사** 내에서 합니다 **데이터 집합 디자이너**합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-global-query-to-a-dataset"></a>전역 쿼리 데이터 집합에 추가 하려면  
  
1.  데이터 집합을 엽니다는 **데이터 집합 디자이너**합니다. 자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)합니다.  
  
2.  끌어서를 **쿼리** 에서 **데이터 집합** 탭의 **도구 상자** 의 빈 영역으로는 **데이터 집합 디자이너**.  
  
     합니다 [Tableadapter 편집](../data-tools/editing-tableadapters.md) 열립니다.  
  
3.  쿼리를 사용 하 여에 대 한 연결을 선택 합니다. 목록에서 하나를 선택 하거나 새 연결을 만들 수 있습니다. 새 연결을 만든 경우에 응용 프로그램 구성 파일에 저장 하는 옵션을 해야 합니다. 자세한 내용은 [방법: 저장 및 연결 문자열 편집](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)합니다.  
  
4.  SQL 문 또는 저장된 프로시저를 사용할 것인지를 선택 합니다.  
  
5.  저장된 프로시저를 사용 하 여 선택, 합니다 **쿼리 형식 선택** 페이지 마법사의 선택한 다음 쿼리 유형을 선택 **다음**합니다.  
  
6.  예를 들어 원하는 작업을 수행 하는 쿼리를 제공 `SELECT COUNT(*) AS CustomerCount FROM Customers`합니다.  
  
    > [!NOTE]
    >  직접 쿼리를 끌어 놓으면 합니다 **데이터 집합 디자이너** 스칼라 (단일) 값만 반환 하는 메서드를 만듭니다. 쿼리 또는 저장된 프로시저를 선택 하면 보다 단일 값을 반환할 수 있습니다, 하는 동안 마법사에서 만든 메서드는 단일 값을 반환 됩니다. 예를 들어 쿼리는 반환된 된 데이터의 첫 번째 행의 첫 번째 열을 반환할 수 있습니다.  
  
7.  마법사를 완료 합니다. 쿼리에 추가할 합니다 **데이터 집합 디자이너**합니다. 쿼리 실행에 대 한 자세한 내용은 [방법: TableAdapter 쿼리 실행](http://msdn.microsoft.com/library/c7518855-f896-41c1-b3de-1a8116280593)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Tableadapter 만들기 및 구성](../data-tools/create-and-configure-tableadapters.md)   
 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [형식화 된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [방법: Windows Forms BindingNavigator 컨트롤을 사용 하 여 데이터를 이동 합니다.](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)