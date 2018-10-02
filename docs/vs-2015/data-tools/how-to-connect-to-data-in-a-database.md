---
title: '방법: 데이터베이스의 데이터에 연결 | Microsoft Docs'
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
- databases, connecting to
- data sources, databases
- data [Visual Studio], connecting to databases
- data sources, creating
- database connections
ms.assetid: 6c56e54e-8834-4297-85aa-cc1a443ba556
caps.latest.revision: 55
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 72b278305995e2edb86e612e0c5c3789c8ce756a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549436"
---
# <a name="how-to-connect-to-data-in-a-database"></a>방법: 데이터베이스의 데이터에 연결
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio를 사용하여 응용 프로그램을 데이터베이스에 연결할 수 있습니다. 데이터 연결을 만들면 데이터베이스의 데이터와 상호 작용하기 위해 응용 프로그램이 사용하는 데이터 모델이 Visual Studio에서 생성됩니다. 데이터 모델의 개체에 표시 된 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)합니다. 데이터 바인딩된 컨트롤에서 항목을 끌어 만들 수 있습니다 합니다 **데이터 소스 창** 디자인 화면에 있습니다. 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다.  
  
 이 항목에서는 데이터베이스에 연결하고 다음 유형의 데이터 모델을 만드는 데 적용되는 지침을 제공합니다.  
  
-   데이터 집합  
  
-   EDM(엔터티 데이터 모델)  
  
> [!NOTE]
>  Visual Studio를 사용하여 데이터베이스로부터 LINQ to SQL 클래스를 만들 수도 있습니다. 그러나 LINQ to SQL 클래스에 나타나지 않습니다 합니다 **데이터 원본** 창 및 데이터 바인딩된 컨트롤을 만드는 데 디자이너로 직접 끌어 올 수 없습니다. 데이터베이스에서 LINQ to SQL 클래스 만들기에 대 한 자세한 내용은 참조 하세요. [방법: 만들 매핑된 LINQ to SQL 클래스 테이블 및 뷰 (O/R 디자이너)](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
##  <a name="dataset"></a> 데이터베이스에 연결 및 데이터 집합 만들기  
 데이터베이스에 기반하는 데이터 집합을 만들면 데이터의 프로그래밍 가능한 뷰를 나타내는 일련의 클래스가 Visual Studio에서 만들어집니다. 기본 클래스에서 호출 되는 *형식화 된 데이터 집합*합니다. 형식화된 데이터 집합은 데이터베이스의 테이블을 나타내는 데이터 테이블 개체를 포함합니다. 형식화 된 데이터 집합에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)합니다.  
  
 데이터 집합을 만든 후 데이터 소스 창에서 WPF 또는 Windows Forms 디자이너로 데이터 집합 개체를 끌어 데이터 바인딩된 WPF 또는 Windows Forms 컨트롤을 만들 수 있습니다.  
  
#### <a name="to-connect-your-application-to-a-database-and-create-a-dataset"></a>응용 프로그램을 데이터베이스에 연결하고 데이터 집합을 만들려면  
  
1.  Visual Studio에서 기존 프로젝트를 열거나 새 프로젝트를 만듭니다.  
  
2.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭합니다.  
  
     합니다 **데이터 소스 구성 마법사** 열립니다.  
  
3.  에 **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 클릭 하 고 **다음**합니다.  
  
4.  에 **데이터베이스 모델 선택** 페이지에서 **데이터 집합**를 클릭 하 고 **다음**합니다.  
  
5.  에 **데이터 연결 선택** 페이지의 사용 가능한 연결 목록에서 데이터 연결을 선택 하 고 클릭 **다음**합니다.  
  
     원하는 데이터 연결에 사용할 수 없는 경우의 단계를 수행 하 여 새 연결을 만들 [새 데이터베이스 연결을 만들어](#CreatingDataConnection)합니다.  
  
6.  에 **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 필요에 따라 명확 합니다 **예으로 연결을 저장** 컴파일된에 직접 연결 문자열을 저장 하려는 경우 확인란 응용 프로그램입니다. 기본적으로 연결은 응용 프로그램 구성 파일에 저장됩니다. 자세한 내용은 [방법: 저장 및 연결 문자열 편집](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)합니다.  
  
7.  에 **데이터베이스 개체 선택** 페이지, 응용 프로그램에서 사용할 데이터베이스 개체를 선택 합니다. 기본값을 바꿀 수도 있습니다 **데이터 집합 이름**합니다.  
  
8.  **마침**을 클릭합니다. 방금 만든 데이터 집합에서 제공 됩니다. 합니다 **데이터 원본** 창입니다.  
  
    > [!NOTE]
    >  경우는 **데이터 원본** 창이 열려 있지 않으면, 클릭 **데이터 소스 표시** 에 **데이터** 창을 열려면 메뉴.  
  
9. 항목을 끌어 수 있습니다는 **데이터 원본** 창에서 WPF 디자이너로, Windows Forms 디자이너, 또는 [구성 요소 디자이너](http://msdn.microsoft.com/library/61a3a450-5b15-465e-bd9a-72a6c8c2b282) 데이터 바인딩된 컨트롤을 만듭니다. 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다.  
  
##  <a name="edm"></a> 데이터베이스에 연결 및 엔터티 데이터 모델 만들기  
 데이터베이스에 기반하는 엔터티 데이터 모델을 만들면 데이터의 프로그래밍 가능한 뷰를 나타내는 일련의 클래스가 Visual Studio에서 만들어집니다. 엔터티 데이터 모델 및 ADO.NET Entity Framework에 대 한 자세한 내용은 참조 하십시오 [Entity Framework 개요](http://msdn.microsoft.com/library/a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0)합니다.  
  
 엔터티 데이터 모델을 만든 후 데이터 소스 창에서 WPF Designer로 엔터티 개체를 끌어 데이터 바인딩된 WPF 컨트롤을 만들 수 있습니다.  
  
#### <a name="to-connect-your-application-to-a-database-and-create-an-entity-data-model"></a>응용 프로그램을 데이터베이스에 연결하고 엔터티 데이터 모델을 만들려면  
  
1.  Visual Studio에서 기존 프로젝트를 열거나 새 프로젝트를 만듭니다.  
  
2.  단계를 수행 합니다 **엔터티 데이터 모델 마법사** 데이터베이스에 연결 하는 모델의 내용을 지정 합니다. 자세한 내용은 [방법: 새.edmx 파일을 만들](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)합니다.  
  
3.  완료 한 후 합니다 **엔터티 데이터 모델 마법사**만든 엔터티 데이터 모델 엔터티 데이터 모델 디자이너에서 열리고 데이터 개체를 사용할 수 있습니다, 합니다 **데이터 원본** 창입니다.  
  
    > [!NOTE]
    >  경우는 **데이터 원본** 창이 열려 있지 않으면, 클릭 **데이터 소스 표시** 에 **데이터** 창을 열려면 메뉴.  
  
4.  WPF designer가 열려 있으면 수 이제 항목을 끌면에서 합니다 **데이터 원본** 창에서 디자이너로 엔터티 데이터 모델에 바인딩되는 컨트롤을 만듭니다. 자세한 내용은 [Visual Studio에서 데이터를 바인딩할 WPF 컨트롤](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)합니다.  
  
     Windows Forms 디자이너를 연 경우 항목을 끌 수 없습니다는 **데이터 원본** 디자이너입니다. 엔터티 데이터 모델에 바인딩되는 컨트롤을 만들려면 프로젝트를 빌드하고 엔터티 데이터 모델에 기반하는 개체 데이터 소스를 새로 추가한 후 해당 개체를 디자이너로 끌어 옵니다.  
  
##  <a name="CreatingDataConnection"></a> 새 데이터베이스 연결 만들기  
 사용 하는 경우는 **데이터 소스 구성 마법사**또는 **엔터티 데이터 모델 마법사**, 사용 하려는 데이터베이스에 대 한 연결을 지정 해야 합니다. 데이터베이스에 대한 연결이 아직 없으면 다음 단계를 수행하여 연결을 만듭니다.  
  
 이 지침에서는 이미 시작한 가정 합니다 **데이터 소스 구성 마법사** 또는 **엔터티 데이터 모델 마법사** 에 설명 된 대로 [데이터베이스에 연결 및 데이터 집합 만들기 ](#dataset) 하 고 [데이터베이스에 연결 및 엔터티 데이터 모델 만들기](#edm)합니다.  
  
#### <a name="to-create-a-new-database-connection"></a>새 데이터베이스 연결을 만들려면  
  
1.  에 **데이터 연결 선택** 페이지의 **데이터 소스 구성 마법사** 또는 **엔터티 데이터 모델 마법사**, 클릭 **새연결**.  
  
     그러면 다음 동작 중 하나가 발생합니다.  
  
    -   Visual Studio에서 데이터 연결을를 이미 만든 경우 합니다 **연결 추가** 대화 상자가 열립니다.  
  
    -   이 Visual Studio에서 만든 첫 번째 데이터 연결 하는 경우는 **데이터 소스 선택** 대화 상자가 표시 됩니다. 에 연결 하 고 클릭 하려는 데이터베이스의 유형을 선택 **확인** 표시할 합니다 **연결 추가** 대화 상자.  
  
2.  에 **연결 추가** 대화 상자에서 요청 된 정보를 입력 합니다. 합니다 **연결 추가** 대화 상자는 데이터 공급자의 각 형식 마다 다릅니다.  
  
    > [!NOTE]
    >  경우 선택한 **데이터 원본** 에 **연결 추가** 대화 상자를 연결 하려는 데이터 원본이 아닌 **변경** 여는 **변경 데이터 원본** 대화 상자를 선택한 다음 다른 데이터 원본입니다.  
  
3.  에 **연결 추가** 대화 상자, 클릭 **확인**합니다.  
  
     반환 합니다 **데이터 연결 선택** 페이지를 **데이터 소스 구성 마법사** 또는 **엔터티 데이터 모델 마법사**합니다.  
  
4.  에 **데이터 연결 선택** 페이지에서 새 데이터 연결이 선택 되어 있는지 확인 하 고 클릭 **다음**합니다.  
  
5.  나머지에서 단계를 완료 합니다 **데이터 소스 구성 마법사** 또는 **엔터티 데이터 모델 마법사**합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 중요한 정보(예: 암호)를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](http://msdn.microsoft.com/library/1471f580-bcd4-4046-bdaf-d2541ecda2f4)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터 소스에 연결](http://msdn.microsoft.com/library/9abc3f92-1be3-4e1a-b360-762dc689650e)