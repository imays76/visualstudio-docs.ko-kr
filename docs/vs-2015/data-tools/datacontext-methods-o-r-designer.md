---
title: DataContext 메서드 (O-r 디자이너) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c149f4e5-3b61-4c33-892e-3e26d47f3eeb
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2ccf32d4af0bd16032c4601b054be6407071753f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49200462"
---
# <a name="datacontext-methods-or-designer"></a>DataContext 메서드(O/R 디자이너)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
DataContext] (assetId:///T:System.Data.Linq.DataContext?qualifyHint=False & autoUpgrade = True) 메서드 (의 컨텍스트에서 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md))의 메서드는는 <xref:System.Data.Linq.DataContext> 저장를 실행 하는 클래스 프로시저 및 데이터베이스에는 함수입니다.  
  
 <xref:System.Data.Linq.DataContext> 클래스는 SQL Server 데이터베이스와 해당 데이터베이스에 매핑되는 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 엔터티 클래스 간의 연결 통로 역할을 하는 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 클래스입니다. <xref:System.Data.Linq.DataContext> 클래스에 연결 문자열 정보 및 데이터베이스에 연결 하 고 데이터베이스에서 데이터를 조작 하기 위한 메서드가 포함 되어 있습니다. 기본적으로 <xref:System.Data.Linq.DataContext> 같은 호출할 수 있는 여러 메서드를 포함 하는 클래스를 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 업데이트 된 데이터를 전송 하는 메서드 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 데이터베이스로 클래스. 추가로 만들 수 있습니다 <xref:System.Data.Linq.DataContext> 저장된 프로시저 및 함수에 매핑되는 메서드. 즉 이러한 사용자 지정 메서드를 호출하면 <xref:System.Data.Linq.DataContext> 메서드가 매핑되는 데이터베이스의 저장 프로시저 또는 함수가 실행됩니다. 클래스를 확장하는 메서드를 추가하는 것처럼 <xref:System.Data.Linq.DataContext> 클래스에 새 메서드를 추가할 수 있습니다. 그러나에 대 한 토론에 <xref:System.Data.Linq.DataContext> 컨텍스트에서 메서드를 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], 것을 <xref:System.Data.Linq.DataContext> 논의 중인 해당 저장된 프로시저 및 함수에 매핑되는 메서드.  
  
## <a name="methods-pane"></a>메서드 창  
 저장 프로시저 및 함수에 매핑되는 <xref:System.Data.Linq.DataContext> 메서드는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 메서드 창에 표시됩니다. 메서드 창 옆에 있는 창입니다 합니다 **엔터티** 창 (주 디자인 화면). 메서드 창 모두 나열 <xref:System.Data.Linq.DataContext> 메서드를 사용 하 여 만든는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]합니다. 기본적으로 메서드 창은 비어 있습니다. 저장 프로시저나 함수를 끌어 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 만들려면 <xref:System.Data.Linq.DataContext> 메서드 및 메서드 창을 채웁니다. 자세한 내용은 [방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 만들기 메서드](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)합니다.  
  
> [!NOTE]
>  열기 및 마우스 오른쪽 단추로 클릭 하 여 메서드 창 닫기 합니다 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 클릭 한 다음 **메서드 창 숨김** 또는 **메서드 창 표시**, 하거나 바로 가기 키 CTRL+1 사용 하 여 합니다.  
  
## <a name="two-types-of-datacontext-methods"></a>DataContext 메서드의 두 가지 형식  
 DataContext 메서드는 데이터베이스의 저장 프로시저와 함수에 매핑되는 메서드로 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 메서드 창에서 만들고 추가할 수 있습니다. 두 가지 유형의 가지 <xref:System.Data.Linq.DataContext> ; 하나 이상의 결과 집합을 반환 하는 메서드와 그렇지 않은 것:  
  
-   결과 집합을 하나 이상 반환하는 <xref:System.Data.Linq.DataContext> 메서드  
  
     응용 프로그램이 저장 프로시저 및 함수를 데이터베이스에서 실행하고 결과를 반환하는 작업만 수행할 때 이 <xref:System.Data.Linq.DataContext> 메서드를 만듭니다. 자세한 내용은 [방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 만들기 메서드](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md), System.Data.Linq.ISingleResult\<T >를 및 <xref:System.Data.Linq.IMultipleResults>합니다.  
  
-   특정 엔터티 클래스에 대한 Inserts, Updates, Deletes 등과 같이 결과 집합을 반환하지 않는 <xref:System.Data.Linq.DataContext> 메서드  
  
     이 유형의 만들려면 <xref:System.Data.Linq.DataContext> 기본값을 사용 하는 대신 저장된 프로시저를 실행할 수 있는 응용 프로그램에서 메서드 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 저장에 대 한 동작 엔터티 클래스와 데이터베이스 간에 데이터를 수정 합니다. 자세한 내용은 [방법: 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 하는 저장된 프로시저를 할당](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)합니다.  
  
## <a name="return-types-of-datacontext-methods"></a>DataContext 메서드의 반환 형식  
 저장된 프로시저 및 함수를 끌어 오면 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], 생성 된 반환 형식 <xref:System.Data.Linq.DataContext> 메서드 항목을 놓는 위치에 따라 합니다. 만듭니다 항목을 기존 엔터티 클래스 위에 직접 놓으면를 <xref:System.Data.Linq.DataContext> 엔터티 클래스의 반환 형식과 메서드를 삭제 항목의 빈 영역에는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] (창) 중 하나를 만듭니다를 <xref:System.Data.Linq.DataContext> 반환 하는 메서드는 자동으로 생성 된 형식입니다. 만든 자동 생성 형식의 이름은 저장 프로시저 또는 함수가 반환한 필드에 매핑되는 저장 프로시저 또는 함수의 이름 및 속성과 일치합니다.  
  
> [!NOTE]
>  메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다. 반환 형식을 검사 하거나 변경 하는 <xref:System.Data.Linq.DataContext> 메서드를 선택 하 고 검사 합니다 **반환 형식** 속성에는 **속성** 창. 자세한 내용은 [방법: DataContext 메서드 (O/R 디자이너)의 반환 형식을 변경](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)합니다.  
  
 데이터베이스에서 O/R 디자이너 화면으로 끌어 오는 개체는 데이터베이스의 개체 이름을 기초로 이름이 자동으로 지정됩니다. 같은 개체를 두 번 이상 끌어 오면 이름을 구별할 수 있도록 새 이름 끝에 숫자가 추가됩니다. 데이터베이스 개체 이름에 공백이 포함되어 있거나 Visual Basic 또는 C#에서 지원되지 않는 문자가 사용되었으면 해당 공백이나 잘못된 문자가 밑줄로 대체됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [저장된 프로시저](http://msdn.microsoft.com/library/4d23dd7a-a85f-44ff-a717-af7d0950c0fc)   
 [방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 메서드 만들기](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)   
 [방법: 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 하는 저장된 프로시저를 할당 합니다.](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)   
 [연습: 사용자 지정 삽입, 업데이트 하 고 엔터티 클래스의 동작을 삭제](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)

