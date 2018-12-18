---
title: N 계층 응용 프로그램에서 Tableadapter에 코드 추가 | Microsoft Docs
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
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2b5302790d694c23da9e5385adf43c185dc66583
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49207677"
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>n 계층 응용 프로그램에서 TableAdapter에 코드 추가
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
기능을 확장할 수 있습니다는 `TableAdapter` 에 대 한 partial 클래스 파일을 만들어 합니다 `TableAdapter` 코드를 추가 하 (코드를 추가 하는 대신 합니다 *DatasetName*. DataSet.Designer 파일)입니다. Partial 클래스를 여러 실제 파일에서 나눌 특정 클래스에 대 한 코드를 사용 합니다. 자세한 내용은 [부분](http://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448) 하거나 [partial (형식)](http://msdn.microsoft.com/library/27320743-a22e-4c7b-b0b3-53afe3607334)합니다.  
  
 정의 하는 코드를 `TableAdapter` 변경 될 때마다 생성 됩니다 합니다 `TableAdapter` (에 [만들기 및 형식화 된 데이터 집합 편집](../data-tools/creating-and-editing-typed-datasets.md)). 구성을 수정 하는 마법사를 실행 하는 동안 변경 된 경우에이 코드는 생성 된 `TableAdapter`합니다. 코드를 다시 생성 하는 동안 삭제를 방지 하기 위해를 `TableAdapter`, partial 클래스 파일의 코드를 추가 합니다 `TableAdapter`합니다.  
  
 기본적으로 데이터 집합을 분리 한 후 및 `TableAdapter` 결과 코드는 각 프로젝트의 개별 클래스 파일입니다. 원래 프로젝트에 이라는 파일로 *DatasetName*합니다. Designer.vb (또는 *DatasetName*합니다. 포함 된 Designer.cs)는 `TableAdapter` 코드입니다. 지정 된 프로젝트를 **데이터 집합 프로젝트** 속성이 라는 파일로 *DatasetName*합니다. DataSet.Designer.vb (또는 *DatasetName*합니다. DataSet.Designer.cs) 데이터 집합 코드를 포함 하는 합니다.  
  
> [!NOTE]
>  데이터 집합을 분리할 때는 및 `TableAdapter`s (설정 하 여 합니다 **데이터 집합 프로젝트** 속성), 프로젝트의 기존 부분 데이터 집합 클래스가 자동으로 이동 되지 것입니다. 기존 데이터 집합 부분 클래스는 데이터 집합 프로젝트에 수동으로 이동 해야 합니다.  
  
> [!NOTE]
>  합니다 [만들기 및 편집 형식화 된 데이터 집합](../data-tools/creating-and-editing-typed-datasets.md) 생성 하기 위한 기능을 제공 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.RowChanging> 유효성 검사가 필요한 경우 이벤트 처리기입니다. 자세한 내용은 [n 계층 데이터 집합에 유효성 검사 추가](../data-tools/add-validation-to-an-n-tier-dataset.md)합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>N 계층 응용 프로그램에서 TableAdapter에 사용자 코드를 추가 하려면  
  
1.  .Xsd 파일을 포함 하는 프로젝트를 찾습니다 (합니다 [만들기 및 형식화 된 데이터 집합 편집](../data-tools/creating-and-editing-typed-datasets.md)).  
  
2.  두 번 클릭 합니다 **.xsd** 열려는 파일을 [만들기 및 형식화 된 데이터 집합 편집](../data-tools/creating-and-editing-typed-datasets.md).  
  
3.  마우스 오른쪽 단추로 클릭 합니다 `TableAdapter` 에 코드를 추가 하 고 클릭 하려는**코드 보기**합니다.  
  
     Partial 클래스는 생성 되 고 코드 편집기에서 열립니다.  
  
4.  Partial 클래스 선언 내에 코드를 추가 합니다.  
  
5.  다음 예제에서는 코드를 추가 하는 위치를 `CustomersTableAdapter` 에 `NorthwindDataSet`:  
  
    ```vb  
    Partial Public Class CustomersTableAdapter  
        ' Add code here to add functionality   
        ' to the CustomersTableAdapter.  
    End Class  
    ```  
  
    ```csharp  
    public partial class CustomersTableAdapter  
    {  
        // Add code here to add functionality  
        // to the CustomersTableAdapter.  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)   
 [N 계층 응용 프로그램에서 데이터 집합에 코드 추가](../data-tools/add-code-to-datasets-in-n-tier-applications.md)   
 [Tableadapter](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)   
 [TableAdapterManager 개요](http://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)   
 [계층적 업데이트 개요](http://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)   
 [데이터 응용 프로그램 만들기](../data-tools/creating-data-applications.md)

