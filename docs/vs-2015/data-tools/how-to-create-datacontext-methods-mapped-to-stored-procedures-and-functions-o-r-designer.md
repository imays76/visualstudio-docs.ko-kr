---
title: '방법: 저장된 프로시저 및 함수 (O-r 디자이너)에 매핑된 DataContext 메서드 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 62d250946e634627c16dbd3b56fce370c11e1f3f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551769"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 메서드 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 저장된 프로시저 및 함수 (O-r 디자이너)에 매핑된 DataContext 만들기 메서드](https://docs.microsoft.com/visualstudio/data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer)합니다.  
  
  
저장된 프로시저 및 함수에 추가할 수 있습니다 합니다 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 으로 <xref:System.Data.Linq.DataContext> 메서드. 메서드를 호출 하 고 필요한 매개 변수에 전달 하면 데이터베이스의 저장된 프로시저 또는 함수를 실행 및 반환 형식으로 데이터를 반환 합니다 <xref:System.Data.Linq.DataContext> 메서드. 에 대 한 자세한 내용은 <xref:System.Data.Linq.DataContext> 메서드를 참조 하세요 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
> [!NOTE]
>  또한 변경 내용을 엔터티 클래스에서 데이터베이스로 저장한 경우 저장 프로시저를 사용하여 삽입, 업데이트 및 삭제를 수행하는 기본 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 런타임 동작을 재정의할 수 있습니다. 자세한 내용은 [방법: 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 하는 저장된 프로시저를 할당](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)합니다.  
  
## <a name="creating-datacontext-methods"></a>DataContext 메서드 만들기  
 만들 수 있습니다 <xref:System.Data.Linq.DataContext> 끌어서 메서드 저장 프로시저 또는 함수를 **서버 탐색기/데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]합니다.  
  
> [!NOTE]
>  생성된 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]에서 저장 프로시저 또는 함수를 놓는 위치에 따라 달라집니다. 항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 항목을 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 빈 영역에 놓으면 자동으로 생성된 형식을 반환하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 반환 형식을 변경할 수 있습니다는 <xref:System.Data.Linq.DataContext> 메서드 창에 추가한 후 메서드. 반환 형식을 검사 하거나 변경 하는 <xref:System.Data.Linq.DataContext> 메서드를 선택 하 고 검사 합니다 **반환 형식** 속성에는 **속성** 창. 자세한 내용은 [방법: DataContext 메서드 (O/R 디자이너)의 반환 형식을 변경](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>자동으로 생성된 형식을 반환하는 DataContext 메서드를 만들려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**를 확장 합니다 **Stored Procedures** 사용 중인 데이터베이스의 노드.  
  
2.  원하는 저장 프로시저를 찾아 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 빈 영역으로 끌어 옵니다.  
  
     합니다 <xref:System.Data.Linq.DataContext> 메서드를 자동으로 생성 된 반환 형식을 사용 하 여 만들어지고 나타나는 합니다 **메서드** 창.  
  
#### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>엔터티 클래스의 반환 형식을 갖는 DataContext 메서드를 만들려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**를 확장 합니다 **Stored Procedures** 사용 중인 데이터베이스의 노드.  
  
2.  원하는 저장 프로시저를 찾아 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 기존 엔터티 클래스로 끌어 옵니다.  
  
     <xref:System.Data.Linq.DataContext> 메서드는 선택한 엔터티 클래스의 반환 형식을 사용 하 여 만들어지고 나타나는 합니다 **메서드** 창.  
  
> [!NOTE]
>  기존 반환 형식을 변경 하는 방법은 <xref:System.Data.Linq.DataContext> 메서드를 참조 하세요 [방법: DataContext 메서드 (O/R 디자이너)의 반환 형식을 변경](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Visual Basic의 LINQ 소개](http://msdn.microsoft.com/library/3047d86e-0d49-40e2-928b-dc02e46c7984)   
 [방법: C#에서 LINQ 쿼리 작성](http://msdn.microsoft.com/library/45e47fcc-cfa1-4b72-b161-d038ae87bd23)

