---
title: '연습: 단일 테이블 상속 (O-r 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 63bc6328-e0df-4655-9ce3-5ff74dbf69a4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 943b75c9c5f9c0c32ab02b5e73c07282728e0beb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49864733"
---
# <a name="walkthrough-create-linq-to-sql-classes-by-using-single-table-inheritance-or-designer"></a>연습: 단일 테이블 상속 (O/R 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기
합니다 [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 관계형 시스템에서 일반적으로 구현 되므로 단일 테이블 상속을 지원 합니다. 이 연습에서 제공한 일반 단계를 다룹니다를 [방법: O/R 디자이너를 사용 하 여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md) 항목에서 상속 사용을 보여 주기 위해 몇 가지 실제 데이터를 제공 하 고는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.

 이 연습에서는 다음 작업을 수행할 수 있습니다.

- 데이터베이스 테이블을 만들고 그 안에 데이터를 추가합니다.

- Windows Forms 응용 프로그램을 만듭니다.

- [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 파일을 프로젝트에 추가합니다.

- 새 엔터티 클래스를 만듭니다.

- 상속을 사용하도록 엔터티 클래스를 구성합니다.

- 상속된 클래스를 쿼리합니다.

- Windows Form에 데이터를 표시합니다.

## <a name="create-a-table-to-inherit-from"></a>상속 하는 테이블 만들기
 만든 작은 상속의 작동 원리를 보려면 `Person` 테이블, 기본 클래스로 사용을 만든 다음는 `Employee` 에서 상속 된 개체입니다.

### <a name="to-create-a-base-table-to-demonstrate-inheritance"></a>상속을 보여 주기 위한 기본 테이블을 만들려면

1.  **서버 탐색기** 또는 **데이터베이스 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **테이블** 노드와 클릭 **새 테이블 추가**합니다.

    > [!NOTE]
    >  Northwind 데이터베이스 또는 테이블을 추가할 수 있는 기타 데이터베이스를 사용할 수 있습니다.

2.  에 **테이블 디자이너**, 테이블에는 다음 열을 추가 합니다.

    |열 이름|데이터 형식|Null 허용|
    |-----------------|---------------|-----------------|
    |**ID**|**int**|**False**|
    |**Type**|**int**|**True**|
    |**FirstName**|**nvarchar(200)**|**False**|
    |**LastName**|**nvarchar(200)**|**False**|
    |**관리자**|**int**|**True**|

3.  ID 열을 기본 키로 설정합니다.

4.  테이블을 저장 하 고 이름을 **Person**합니다.

## <a name="add-data-to-the-table"></a>테이블에 데이터 추가
 속성이 올바르게 구성되었는지 확인하기 위해서는 단일 테이블 상속에서 각 클래스에 대한 몇 가지 데이터가 테이블에 필요합니다.

### <a name="to-add-data-to-the-table"></a>테이블에 데이터를 추가하려면

1.  데이터 뷰에서 테이블을 엽니다. (마우스 오른쪽 단추로 클릭 합니다 **Person** 테이블의 **서버 탐색기** 또는 **데이터베이스 탐색기** 클릭 **테이블 데이터 표시**.)

2.  다음 데이터를 테이블로 복사합니다. (복사한 다음 전체 행을 선택 하 여 테이블에 붙여 넣을 수는 **결과** 창입니다.)

    ||||||
    |-|-|-|-|-|
    |**ID**|**Type**|**FirstName**|**LastName**|**관리자**|
    |**1**|**1**|**Anne**|**월리스**|**NULL**|
    |**2**|**1**|**Carlos**|**Grilo**|**NULL**|
    |**3**|**1**|**Yael**|**Peled**|**NULL**|
    |**4**|**2**|**Gatis**|**Ozolins**|**1**|
    |**5**|**2**|**목록의 경우 Andreas**|**Hauser**|**1**|
    |**6**|**2**|**Tiffany**|**Phuvasate**|**1**|
    |**7**|**2**|**Alexey**|**Orekhov**|**2**|
    |**8**|**2**|**Michał**|**Poliszkiewicz**|**2**|
    |**9**|**2**|**타이**|**파견 된 킴이**|**2**|
    |**10**|**2**|**Fabricio**|**Noriega**|**3**|
    |**11**|**2**|**구재석**|**Martin**|**3**|
    |**12**|**2**|**박 단은**|**Kwok 추가**|**3**|

## <a name="create-a-new-project"></a>새 프로젝트 만들기
 테이블을 만든 후에는 상속 구성을 보여 주기 위한 새 프로젝트를 만듭니다.

### <a name="to-create-the-new-windows-forms-application"></a>새 Windows Forms 응용 프로그램을 만들려면

1. Visual Studio에서에 **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.

2. 확장 **Visual C#** 하거나 **Visual Basic** 왼쪽 창에서 선택한 **Windows Desktop**합니다.

3. 가운데 창에서 선택 합니다 **Windows Forms 앱** 형식 프로젝션 합니다.

4. 프로젝트 이름을 **InheritanceWalkthrough**를 선택한 후 **확인**합니다.

     합니다 **InheritanceWalkthrough** 프로젝트에 추가한 만들어지면 **솔루션 탐색기**합니다.

## <a name="add-a-linq-to-sql-classes-file-to-the-project"></a>LINQ to SQL 클래스 파일을 프로젝트에 추가

### <a name="to-add-a-linq-to-sql-file-to-the-project"></a>LINQ to SQL 파일을 프로젝트에 추가 하려면

1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.

2.  클릭 합니다 **LINQ to SQL 클래스** 템플릿과 클릭 **추가**합니다.

     합니다 *.dbml* 파일이 프로젝트에 추가 됩니다 하며 **O/R 디자이너** 열립니다.

## <a name="create-the-inheritance-by-using-the-or-designer"></a>O/R 디자이너를 사용 하 여 상속 만들기
 드래그 하 여 상속 구성를 **상속** 에서 개체를 **도구 상자** 디자인 화면으로 합니다.

### <a name="to-create-the-inheritance"></a>상속을 만들려면

1.  **서버 탐색기** 또는 **데이터베이스 탐색기**로 이동 합니다 **Person** 앞에서 만든 테이블.

2.  끌어서 합니다 **Person** 테이블을 합니다 **O/R 디자이너** 디자인 화면.

3.  초를 끌어 **Person** 테이블을 **O/R 디자이너** 하 고 해당 이름을 변경 **직원**합니다.

4.  삭제를 **관리자** 속성을 **사용자** 개체입니다.

5.  삭제를 **형식**, **ID**, **FirstName**, 및 **LastName** 속성을 **직원** 개체입니다. (즉, 모든 속성을 제외 하 고 삭제할 **Manager**.)

6.  **Object Relational Designer** 탭을 **도구 상자**, 만들기를 **상속** 간에 **사용자** 및  **직원** 개체입니다. 이렇게 하려면 클릭 합니다 **상속** 항목에 **도구 상자** 마우스 단추를 놓습니다. 를 클릭 합니다 **직원** 개체 차례로 **사용자** 개체를 **O/R 디자이너**합니다. 상속 선의 화살표가 그러면 합니다 **Person** 개체입니다.

7.  클릭 합니다 **상속** 디자인 화면에서 선을 합니다.

8.  설정 된 **Discriminator Property** 속성을 **형식**합니다.

9. 설정 된 **Derived Class Discriminator Value** 속성을 **2**합니다.

10. 설정 된 **Base Class Discriminator Value** 속성을 **1**합니다.

11. 설정 된 **Inheritance Default** 속성을 **Person**합니다.

12. 프로젝트를 빌드합니다.

## <a name="query-the-inherited-class-and-display-the-data-on-the-form"></a>상속된 된 클래스를 쿼리하고 폼에 데이터를 표시 합니다.
 이제 개체 모델에서 특정 클래스에 대 한 쿼리는 폼에 일부 코드를 추가 합니다.

### <a name="to-create-a-linq-query-and-display-the-results-on-the-form"></a>LINQ 쿼리를 만들고 폼에 결과를 표시하려면

1.  끌어서를 **ListBox** 끌어다 **Form1**합니다.

2.  폼을 두 번 클릭하여 `Form1_Load` 이벤트 처리기를 만듭니다.

3.  다음 코드를 `Form1_Load` 이벤트 처리기에 추가합니다.

    ```vb
    Dim dc As New DataClasses1DataContext
    Dim results = From emp In dc.Persons _
        Where TypeOf emp Is Employee _
        Select emp

    For Each Emp As Employee In results
        ListBox1.Items.Add(Emp.LastName)
    Next
    ```

    ```csharp
    NorthwindDataContext dc = new DataClasses1DataContext();
    var results = from emp in dc.Persons
                  where emp is Employee
                  select emp;

    foreach(Employee Emp in results)
    {
        listBox1.Items.Add(Emp.LastName)
    }
    ```

## <a name="test-the-application"></a>응용 프로그램 테스트
 응용 프로그램을 실행 하 고 목록 상자에 표시 된 레코드는 모든 직원에 게 확인 (레코드 2 값이 있는 해당 **형식** 열).

### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면

1.  **F5**키를 누릅니다.

2.  확인만 기록 하는 2 값이 있는 해당 **형식** 열이 표시 됩니다.

3.  폼을 닫아 디버깅을 (에 **디버깅할** 메뉴에서 클릭 **디버깅 중지**.)

## <a name="see-also"></a>참고자료

- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [연습:는 LINQ to SQL 클래스 (O-r 디자이너) 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [방법: Visual Basic 또는 C#에서 개체 모델 생성](/dotnet/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp)