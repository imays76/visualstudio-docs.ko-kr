---
title: Tableadapter 편집 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.datasource.dbtablefunctionwizard
- vs.datasource.datacomponentquerywizard
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], data component queries
- data [Visual Studio], TableAdapters
- TableAdapter Query Configuration Wizard
- data [Visual Studio], table adapter queries
ms.assetid: 8c06b306-24d0-4521-948d-07e3b7badd95
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: faeac90c92675c897774cc3650575cd60f5be991
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49288407"
---
# <a name="editing-tableadapters"></a>Tableadapter 편집
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

어댑터의 테이블의 스키마를 변경 하는 경우가 있습니다. 이 작업을 수행 하려면 어댑터의 기본 수정 `Fill` 메서드. Tableadapter는 main를 사용 하 여 만들어진 `Fill` 관련된 데이터 테이블의 스키마를 정의 하는 메서드. 주 `Fill` 쿼리를 기반으로 하는 메서드 또는 원래 TableAdapter를 구성할 때 입력 저장된 프로시저;에서 데이터 테이블에서 첫 번째 (최상위) 메서드가 표시 되는 [만들기 및 형식화 된 데이터 집합 편집](../data-tools/creating-and-editing-typed-datasets.md)합니다.  
  
 ![여러 개의 쿼리가 있는 TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")  
  
 TableAdapter에 수행한 모든 변경 내용을 주 `Fill` 메서드는 연결된 된 데이터 테이블의 스키마에 반영 됩니다. 예를 들어, 기본에서 쿼리에서 열 제거 `Fill` 메서드 또한 연결된 된 데이터 테이블에서 열을 제거 합니다. 또한 기본에서 열을 제거 `Fill` 메서드는 TableAdapter에 대 한 모든 추가 쿼리에서 열을 제거 합니다.  
  
 사용할 수는 **TableAdapter 쿼리 구성 마법사** 만들고 TableAdapter에 대 한 추가 쿼리를 편집 합니다. 이러한 추가 쿼리는 스칼라 값을 반환 하지 않는 한 테이블 스키마를 준수 해야 합니다.  지정 된 이름이 추가 쿼리 (예를 들어 `CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, "Seattle")`.)  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-with-a-new-query"></a>새 쿼리를 사용 하 여 TableAdapter 쿼리 구성 마법사를 시작 하려면  
  
1.  데이터 집합을 엽니다는 **데이터 집합 디자이너**합니다.  
  
2.  끌어 새 쿼리를 만드는 경우는 **쿼리** 에서 개체를 **데이터 집합** 탭을 **도구 상자** 에 <xref:System.Data.DataTable>를 선택 또는 **추가 쿼리**TableAdapter의 바로 가기 메뉴에서. 끌 수도 있습니다는 **쿼리** 개체의 빈 영역에는 **데이터 집합 디자이너**, 없이 연결 된 TableAdapter를 만듭니다 <xref:System.Data.DataTable>합니다. 이러한 쿼리 (스칼라) 단일 값 반환 또는 UPDATE, INSERT 실행으로 제한 됩니다 또는 데이터베이스에 대해 명령을 삭제 합니다. 자세한 내용은 [방법: TableAdapter에 전역 쿼리 추가](../data-tools/how-to-add-global-queries-to-a-tableadapter.md)합니다.  
  
3.  에 **데이터 연결 선택** 선택 페이지 또는 쿼리를 사용 하 여 연결을 만듭니다.  
  
    > [!NOTE]
    >  이 페이지는 디자이너를 사용 하려면 적절 한 연결을 확인할 수 없는 경우 또는 연결이 없는 경우에 나타납니다.  
  
4.  에 **명령 유형을 선택** 페이지의 데이터베이스에서 데이터를 가져오는 다음 방법 중에서 선택 합니다.  
  
    -   **SQL 문을 사용 하 여** 데이터베이스에서 데이터를 선택 하는 SQL 문을 입력할 수 있습니다.  
  
    -   **새 저장된 프로시저를 만들** -마법사에서 새 저장된 프로시저 만들기 (데이터베이스)에 지정 된 SELECT 문을 기반으로 하려면이 옵션을 선택 합니다.  
  
    -   **기존 저장된 프로시저를 사용 하 여** -쿼리를 실행 하는 경우 기존 저장된 프로시저를 실행 하려면이 옵션을 선택 합니다.  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-on-an-existing-query"></a>기존 쿼리는 TableAdapter 쿼리 구성 마법사를 시작 하려면  
  
-   기존 TableAdapter 쿼리를 편집 하는 경우 쿼리를 마우스 오른쪽 단추로 **구성** 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  TableAdapter를 재구성 TableAdapter의 주 쿼리를 마우스 오른쪽 단추로 클릭 하 고 <xref:System.Data.DataTable> 스키마 TableAdapter에서 추가 쿼리를 마우스 오른쪽 단추로 클릭 하는 반면 선택한 쿼리 구성만 합니다. 합니다 **TableAdapter 구성 마법사** TableAdapter 정의 다시 구성, **TableAdapter 쿼리 구성 마법사** 선택한 쿼리만 다시 구성 합니다.  
  
## <a name="running-the-wizard"></a>마법사 실행  
 으로 쿼리를 끌어 합니다 **데이터 집합 디자이너**, 또는 기존 쿼리 (첫 번째 쿼리 아래에 나열 된 모든 쿼리)를 구성 합니다.  
  
 TableAdapter의 첫 번째 쿼리가 TableAdapter의 주 쿼리입니다. 열립니다이 주 쿼리를 편집 합니다 **TableAdapter 구성 마법사** TableAdapter의 데이터 테이블의 스키마가 편집 합니다. 주 쿼리 아래에 나열 된 모든 쿼리는 추가 및 사용 하 여 구성 합니다 **TableAdapter 쿼리 구성 마법사**합니다. 마법사를 실행 하는 방법은 참조 하세요 [방법: TableAdapter 쿼리 구성 마법사 시작](http://msdn.microsoft.com/library/fc7b468e-3417-48a4-a8aa-cace8f99c24a)합니다.  
  
## <a name="choose-your-data-connection"></a>데이터 연결 선택  
 연결 목록에서 기존 연결을 선택 하거나 클릭 **새 연결** 데이터베이스에 연결을 만듭니다.  
  
 완료 되 면를 **연결 속성** 대화 상자를 **연결 세부 정보** 영역에 연결 문자열 뿐만 아니라 선택한 공급자에 대 한 읽기 전용 정보 표시 됩니다.  
  
## <a name="save-the-connection-string-to-the-application-configuration-file"></a>응용 프로그램 구성 파일에 연결 문자열 저장  
 선택 **예,으로 연결을 저장** 응용 프로그램 구성 파일에 연결 문자열을 저장 합니다. 연결의 이름을 입력하거나 제공된 기본값을 사용합니다.  
  
 응용 프로그램 구성 파일에 연결 문자열을 저장하면 데이터베이스 연결이 변경되는 경우의 응용 프로그램 유지 관리 프로세스를 간소화할 수 있습니다. 데이터베이스 연결이 변경되는 경우 응용 프로그램 구성 파일에서 연결 문자열을 편집하면 됩니다. 그러면 소스 코드를 편집하고 응용 프로그램을 다시 컴파일할 필요가 없습니다. 응용 프로그램 구성 파일에서 연결 문자열을 편집에 대 한 자세한 내용은 [방법: 저장 및 연결 문자열 편집](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)합니다.  
  
> [!IMPORTANT]
>  정보는 일반 텍스트로 응용 프로그램 구성 파일에 저장됩니다. 중요한 데이터에 대한 무단 액세스 가능성을 줄이려면 데이터를 암호화할 수 있습니다. 자세한 내용은 [암호화 및 암호 해독 데이터](http://msdn.microsoft.com/en-us/22812ae8-e082-4eb1-a29b-21b6ee00c6b5)입니다.  
  
## <a name="use-sql-statements"></a>SQL 문 사용  
 이 섹션을 완료 하는 방법에 설명 합니다 **TableAdapter 쿼리 구성 마법사** 선택 하는 경우를 **SQL 문 사용** 옵션입니다.  
  
## <a name="choose-a-query-type"></a>쿼리 형식 선택  
 마법사에서는 응용 프로그램의 요구 사항에 따라 여러 형식의 쿼리를 만듭니다. 데이터 행(데이터 테이블)을 반환하는 SELECT 쿼리나 스칼라 값(`Count` 또는 `Sum`과 같은 단일 값)을 반환하는 SELECT 쿼리를 선택할 수 있습니다.  
  
 에 **쿼리 형식 선택** 페이지에서 사용 가능한 쿼리 목록에서 만들 쿼리의 형식을 선택 합니다.  
  
> [!NOTE]
>  INSERT, UPDATE 또는 DELETE 문을 만드는 경우 TableAdapter의 `Update` 메서드를 호출할 때 사용되는 TableAdapter의 명령이 바뀌지 않습니다. 예를 들어 쿼리 형식으로 UPDATE를 선택하면 마법사의 이후 단계에서 지정한 이름으로 새 쿼리가 만들어집니다. 이렇게 이름이 지정된 TableAdapter의 메서드를 호출하여 해당 쿼리를 실행합니다. TableAdapter의 `Update` 메서드를 호출하면 원래 TableAdapter를 구성할 때 작성된 문이 실행됩니다.  
  
## <a name="specify-a-sql-query-type-statement"></a>SQL 지정 \<쿼리 형식 > 문  
 에 **SQL 문을 지정할** 페이지에서 쿼리를 호출할 때 실행할 SQL 문을 입력 합니다.  
  
> [!TIP]
>  마법사에 대 한 액세스를 제공 합니다 **쿼리 작성기**, SQL 쿼리를 작성 하는 비주얼 도구입니다. 를 열려면 클릭 합니다 **쿼리 작성기** 단추입니다.  
  
## <a name="choose-methods-to-generate"></a>생성할 메서드 선택  
 이 페이지에서는 마법사가 쿼리에 대해 생성할 메서드를 선택하는 옵션이 제공됩니다.  
  
 **DataTable 채우기**  
 데이터 테이블 채우는 메서드를 만듭니다. 반환된 데이터로 데이터 테이블을 채우기 위해 이 메서드를 호출할 때는 데이터 테이블의 이름을 매개 변수로 전달합니다.  
  
 기본 이름을 변경할 수는 필요에 따라 합니다 **메서드 이름** 상자입니다. 의미 있는 이름을 지정하면 코드에서 이 쿼리를 사용할 때 도움이 될 수 있습니다.  
  
 **DataTable 반환**  
 채워진 데이터 테이블을 반환하기 위한 메서드를 만듭니다. 특정 응용 프로그램에서는 기존 데이터 테이블에 데이터를 채우는 것보다 채워진 데이터 테이블을 반환하는 것이 더 효율적일 수 있습니다.  
  
 기본 이름을 변경할 수는 필요에 따라 합니다 **메서드 이름** 상자입니다.  
  
## <a name="choose-function-name"></a>함수 이름을 선택하십시오.  
 함수의 이름을 입력합니다. TableAdapter 쿼리를 만들면 여기서 입력한 이름의 메서드가 TableAdapter에 추가됩니다. 쿼리를 실행하려면 이 메서드를 호출합니다. 의미 있는 이름을 지정하면 코드에서 이 쿼리를 사용할 때 도움이 됩니다.  
  
> [!NOTE]
>  새 저장 프로시저를 만들 때는 이름 두 개를 입력해야 합니다. 첫 번째 이름은 데이터베이스에서 만드는 저장 프로시저의 이름이고 두 번째 이름은 호출 시 저장 프로시저를 실행하는 TableAdapter의 메서드 이름입니다.  
  
## <a name="create-new-stored-procedures"></a>새 저장 프로시저 만들기  
 이 섹션을 완료 하는 방법에 설명 합니다 **TableAdapter 쿼리 구성 마법사** 선택 하는 경우를 **새 저장된 프로시저 만들기** 옵션입니다.  
  
1.  에 **저장 프로시저 생성** 페이지에서 저장된 프로시저를 호출할 때 실행할 SQL 문을 입력 합니다.  
  
    > [!NOTE]
    >  마법사에 대 한 액세스를 제공 합니다 **쿼리 작성기**, SQL 쿼리를 작성 하는 비주얼 도구입니다. 를 열려면 클릭 합니다 **쿼리 작성기** 단추입니다.  
  
2.  에 **저장된 프로시저 만들기** 페이지에서 다음을 수행 합니다.  
  
    1.  새 저장 프로시저의 이름을 입력합니다.  
  
    2.  기본 데이터베이스에서 저장 프로시저를 만들지 여부를 지정합니다.  
  
        > [!NOTE]
        >  특정 데이터베이스의 보안 설정에 따라 해당 데이터베이스에서 저장 프로시저를 만들 수 있는지 여부가 결정됩니다.  
  
     합니다 **마법사 결과 보기** 페이지는 TableAdapter 쿼리 만들기 결과 보여 줍니다. 마법사에 문제가 발생하는 경우 이 페이지에서 오류 정보가 제공됩니다.  
  
## <a name="use-existing-stored-procedures"></a>기존 저장 프로시저 사용  
 이 섹션을 완료 하는 방법에 설명 합니다 **TableAdapter 쿼리 구성 마법사** 선택 하는 경우를 **기존 저장된 프로시저를 사용 하 여** 옵션.  
  
1.  드롭다운 목록에서 기존 저장된 프로시저를 선택 합니다 **기존 저장된 프로시저를 선택** 마법사의 페이지입니다.  
  
     합니다 **매개 변수** 하 고 **결과** 선택한 저장 프로시저 참조에 대 한 표시 됩니다.  
  
2.  **다음**을 클릭합니다.  
  
## <a name="choose-the-shape-of-data-returned-by-the-stored-procedure"></a>저장 프로시저가 반환하는 데이터의 모양 선택  
 선택한 저장 프로시저가 반환하는 데이터의 형식에 따라 마법사가 TableAdapter 메서드를 만드는 방법이 결정됩니다.  
  
 이 쿼리에서 반환되는 데이터의 형식을 선택합니다.  
  
-   선택 **Tabular data** 열립니다는 **생성할 메서드 선택** 페이지 앞에서 설명한이 도움말 페이지에서 메서드, 메서드 이름 및 페이징 지원을 만들의 형식을 지정할 수 있습니다.  
  
-   선택 **단일 값** 단일 값을 반환 하는 형식화 된 메서드가 만들어집니다. 이 옵션을 열립니다는 **함수 이름을 선택** 앞에서 설명한이 도움말 페이지의 페이지입니다.  
  
-   선택 **값이 없는** 없는 데이터를 반환 하며 저장된 프로시저를 실행 하는 형식화 된 메서드가 만들어집니다. 이 옵션을 열립니다는 **함수 이름을 선택** 앞에서 설명한이 도움말 페이지의 페이지입니다.  
  
## <a name="view-wizards-results"></a>마법사 결과 보기  
 합니다 **마법사 결과 보기** 페이지는 TableAdapter 쿼리 만들기 결과 보여 줍니다. 마법사에 문제가 발생하면 이 페이지에 세부 정보가 표시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)   
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)