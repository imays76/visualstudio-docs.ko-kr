---
title: '방법: 업데이트, 삽입 및 삭제 (O-r 디자이너)를 수행 하는 저장된 프로시저를 할당 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e88224ab-ff61-4a3a-b6b8-6f3694546cac
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a211048e287bd3ef3e45625022f7389e06358e32
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554165"
---
# <a name="how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-or-designer"></a>방법: 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 하는 저장된 프로시저를 할당 합니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 저장된 프로시저를 업데이트, 삽입 및 삭제 (O-r 디자이너)를 수행 합니다. 할당](https://docs.microsoft.com/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)합니다.  
  
  
저장 프로시저를 O/R 디자이너에 추가하여 일반적인 <xref:System.Data.Linq.DataContext> 메서드로 실행할 수 있습니다. 기본값을 재정의 하려면 사용할 수도 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 데이터베이스에 변경 내용을 엔터티 클래스에서 저장 되 면 삭제 및 삽입, 업데이트를 수행 하는 런타임 동작 (호출 하는 경우에 예를 들어를 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 메서드).  
  
> [!NOTE]
>  클라이언트로 다시 보내야 하는 값(예: 저장 프로시저에서 계산된 값)을 저장 프로시저에서 반환하는 경우 저장 프로시저에 출력 매개 변수를 만듭니다. 출력 매개 변수를 사용할 수 없는 경우 O/R 디자이너에서 생성된 재정의를 사용하지 말고 부분 메서드(Partial Method) 구현을 작성합니다. 데이터베이스에서 생성된 값에 매핑되는 멤버는 INSERT 또는 UPDATE 작업이 성공적으로 완료된 후 적절한 값으로 설정되어야 합니다. 자세한 내용은 [는 개발자의 기본 동작 재정의의 책임](http://msdn.microsoft.com/library/c6909ddd-e053-46a8-980c-0e12a9797be1)합니다.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)]은 identity(자동 증분), rowguidcol(데이터베이스에서 생성된 GUID) 및 timestamp 열에 대해 데이터베이스에서 생성된 값을 자동으로 처리합니다. 데이터베이스에서 생성된 값이 다른 형식의 열에 있으면 null 값이라는 예기치 않은 결과가 발생합니다. 데이터베이스에서 생성된 값을 반환하려면 수동으로 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 `true`로 설정하고 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>를 <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync> 또는 <xref:System.Data.Linq.Mapping.AutoSync> 중 하나로 설정해야 합니다.  
  
## <a name="configuring-the-update-behavior-of-an-entity-class"></a>엔터티 클래스의 업데이트 동작 구성  
 기본적으로 삽입, 업데이트 및 삭제와 같은 데이터베이스를 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 엔터티 클래스의 데이터에 대한 변경 내용으로 업데이트하는 논리가 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 런타임에서 제공됩니다. 런타임에서는 열 및 기본 키 정보와 같은 테이블 스키마를 기반으로 기본 삽입, 업데이트 및 삭제 명령을 만듭니다. 기본 동작을 원하지 않는 경우 필요한 삽입, 업데이트를 수행 하기 위한 특정 저장된 프로시저를 할당 하 여 업데이트 동작을 구성할 수 있습니다 및 테이블의 데이터를 조작 하는 데 필요한 삭제 합니다. 엔터티 클래스가 뷰에 매핑되는 때와 같이 기본 동작이 생성되지 않은 경우에도 이렇게 할 수 있습니다. 또한 저장 프로시저를 통해 데이터베이스의 테이블에 액세스해야 하는 경우에 기본 업데이트 동작을 재정의할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-assign-stored-procedures-to-override-the-default-behavior-of-an-entity-class"></a>저장 프로시저를 지정하여 엔터티 클래스의 기본 동작을 재정의하려면  
  
1.  엽니다는 **LINQ to SQL** 디자이너에서 파일입니다. (에서.dbml 파일을 두 번 클릭 **솔루션 탐색기**.)  
  
2.  **서버 탐색기**/**데이터베이스 탐색기**을 확장 하 고 **Stored Procedures** 저장된 프로시저 Insert, Update에 대 한 사용 하려는 찾아서 및/또는 엔터티 클래스의 명령을 삭제 합니다.  
  
3.  저장 프로시저를 O/R 디자이너로 끌어 놓습니다.  
  
     저장 프로시저는 메서드 창에 <xref:System.Data.Linq.DataContext> 메서드로 추가됩니다. 자세한 내용은 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
4.  업데이트 수행을 위해 저장 프로시저를 사용하려는 엔터티 클래스를 선택합니다.  
  
5.  에 **속성** 창 재정의할 선택 (**삽입**를 **업데이트**, 또는 **삭제**).  
  
6.  옆의 줄임표 (...)를 클릭 **사용 하 여 런타임** 열려는 합니다 **동작 구성** 대화 상자.  
  
7.  선택 **사용자 지정**합니다.  
  
8.  원하는 저장된 프로시저를 선택 합니다 **사용자 지정** 목록입니다.  
  
9. 검사 목록 **메서드 인수** 및 **클래스 속성** 되었는지 확인 하는 **메서드 인수** 매핑할 적절 한 **클래스속성**. 원래 메서드 인수 (Original_*ArgumentName*)를 원래 속성 (*PropertyName* (Original)) Update 및 Delete 명령에 대 한 합니다.  
  
    > [!NOTE]
    >  기본적으로 메서드 인수는 이름이 일치하는 경우 클래스 속성에 매핑됩니다. 속성 이름이 변경되어서 더 이상 테이블과 엔터티 클래스 간에 일치하지 않으면 디자이너에서 올바른 매핑을 결정할 수 없는 경우 매핑할 해당 클래스 속성을 선택해야 합니다.  
  
10. 클릭 **확인** 하거나 **적용**합니다.  
  
    > [!NOTE]
    >  계속을 클릭 하면으로 각 클래스/동작 조합에 대 한 동작을 구성할 수 있습니다 **적용** 각 변경 합니다. 클릭 하기 전에 클래스 또는 동작을 변경 하는 경우 **적용**, 모든 변경 내용을 적용할 수 있는 기회 나타납니다 제공 하는 경고 대화 상자.  
  
     되돌리려면 기본 런타임 논리를 사용 하 여 업데이트, 삽입, 업데이트, 옆의 줄임표를 클릭 또는 삭제 명령 합니다 **속성** 창과 선택 **런타임을 사용 하 여** 에  **동작 구성** 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [연습: 저장 프로시저는 Northwind Customers 테이블에 대 한 업데이트 만들기](../data-tools/walkthrough-creating-update-stored-procedures-for-the-northwind-customers-table.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [삽입, 업데이트 및 삭제 작업](http://msdn.microsoft.com/library/26a43a4f-83c9-4732-806d-bb23aad0ff6b)

