---
title: 데이터 응용 프로그램 만들기 | Microsoft Docs
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
- data access [Visual Studio], creating applications
- applications [Visual Studio], data
- data [Visual Studio]
- data [Visual Studio], creating applications
ms.assetid: ab334d5f-4f49-4346-bce0-3325d6130b3e
caps.latest.revision: 41
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 4e5354d167dd6d3a1bef9beeb3dcaaaf24871bab
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49291319"
---
# <a name="creating-data-applications"></a>데이터 응용 프로그램 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio는 데이터에 액세스하는 응용 프로그램을 만드는 과정을 돕는 많은 디자인 타임 도구를 제공합니다. 여기서는 데이터 작업을 하는 응용 프로그램 작성과 관련된 기본 프로세스를 간략하게 살펴봅니다. 이 정보는 자세한 내용을 다루지 않으며 데이터 응용 프로그램의 작성과 관련된 일반적인 정보를 제공하고 이와 관련된 여러 도움말 페이지로 연결되는 링크를 제공하도록 구성되었습니다.  
  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 데이터에 액세스하는 응용 프로그램을 개발할 때의 요구 사항은 경우에 따라 다릅니다. 단순히 폼에 데이터를 표시해야 할 경우가 있으며 다른 응용 프로그램 또는 프로세스와 정보를 공유하는 방법을 찾아야 할 경우도 있습니다.  
  
 데이터로 수행하는 작업이 어떤 것이든, 몇 가지 기본 개념은 이해하고 있어야 합니다. 데이터 처리의 세부 사항에 대해서 모두 알 필요는 없습니다. 예를 들어, 프로그래밍 방식으로 데이터베이스를 만드는 방법은 알 필요가 없을 수 있지만 기본적인 데이터 개념 및 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 사용할 수 있는 데이터 도구(마법사와 디자이너)에 대해 이해하고 있으면 큰 도움이 됩니다.  
  
 일반적인 데이터 응용 프로그램에서는 다음 다이어그램에 표시된 프로세스를 대부분 사용합니다.  
  
 ![데이터 주기 그래픽](../data-tools/media/datacyclegraphicinfo.gif "datacyclegraphicinfo")  
데이터 주기  
  
 응용 프로그램을 작성할 때는 어떤 작업을 완료하고자 하는지 생각하십시오. 다음 단원은 사용 가능한 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 도구 및 개체를 찾는 데 도움이 됩니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]는 이전 다이어그램에 표시되는 몇 가지 프로세스를 단순화하는 마법사를 제공합니다. 예를 들어, 실행 합니다 **데이터 소스 구성 마법사** 데이터에 연결 하 고 데이터를 받을 형식화 된 데이터 집합을 만드는 응용 프로그램에 데이터를 가져올 충분 한 정보를 사용 하 여 응용 프로그램을 제공 합니다.  
  
 신속 하 게 확인 하는 방법 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 데이터 응용 프로그램 개발에 도움이 참조 [연습: 간단한 데이터 응용 프로그램을 만드는](http://msdn.microsoft.com/library/c5d0968c-d86f-4ae9-a2e1-871f208a3bb3)합니다.  
  
## <a name="connecting-to-data"></a>데이터에 연결  
 데이터를 응용 프로그램으로 가져오고 변경 내용을 다시 데이터 소스로 보내려면 일종의 양방향 통신이 이뤄져야 합니다. 이러한 양방향 통신은 주로 데이터 모델의 개체에서 처리합니다.  
  
 예를 들어, `TableAdapter`는 데이터 집합을 사용하는 응용 프로그램을 데이터베이스에 연결하고 <xref:System.Data.Objects.ObjectContext>는 Entity Framework의 엔터티를 데이터베이스에 연결합니다. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서는 응용 프로그램에서 사용 가능한 연결을 만드는 데 도움이 되는 여러 가지 도구를 제공합니다. 응용 프로그램 데이터를 연결 하는 방법에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 데이터를 연결할](../data-tools/connecting-to-data-in-visual-studio.md)합니다.  
  
 참조 데이터 집합을 사용 하 여 응용 프로그램을 데이터베이스에서 데이터를 연결 하는 방법에 알아보려면 [연습: 데이터 (Windows Forms) 데이터베이스에 연결할](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)합니다.  
  
## <a name="preparing-your-application-to-receive-data"></a>데이터를 받기 위해 응용 프로그램 준비  
 응용 프로그램에서 연결되지 않은 데이터 모델을 사용하는 경우 데이터 작업을 하는 동안 응용 프로그램에서 임시로 데이터를 저장해야 합니다. Visual Studio는 응용 프로그램에서 데이터 집합, 엔터티 및 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 개체와 같은 데이터를 임시로 저장하는 데 사용하는 개체를 만드는 데 도움이 되는 도구를 제공합니다.  
  
> [!NOTE]
>  연결되지 않은 데이터 모델을 사용하는 응용 프로그램은 일반적으로 데이터베이스에 연결하고, 데이터를 응용 프로그램으로 가져오는 쿼리를 실행하고, 데이터베이스와의 연결을 끊고, 데이터를 오프라인으로 조작한 다음 데이터베이스에 다시 연결하여 데이터베이스를 업데이트합니다.  
  
 응용 프로그램에서 형식화 된 데이터 집합을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [수신 데이터에 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)합니다. N 계층 응용 프로그램에서 데이터 집합을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [데이터 집합 및 Tableadapter를 다른 프로젝트로 분리](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)합니다.  
  
 데이터 집합을 만드는 방법에 알아보려면의 절차를 완료 [연습: 데이터 집합 디자이너를 사용 하 여 데이터 집합 만들기](../data-tools/walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.  
  
 만드는 방법을 알아보려면 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 의 절차를 완료 하는 개체를 [연습: 만들기 LINQ to SQL 클래스 (O-r 디자이너)](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)합니다.  
  
## <a name="fetching-data-into-your-application"></a>데이터를 응용 프로그램으로 페치  
 응용 프로그램에서 연결되지 않은 데이터 모델을 사용하는지 여부에 관계없이 데이터를 응용 프로그램으로 페치할 수 있어야 합니다. 데이터베이스에 대해 쿼리 또는 저장 프로시저를 실행하여 데이터를 응용 프로그램으로 가져옵니다. 사용 하 여 쿼리 및 저장된 프로시저를 실행 하는 데이터 집합에 데이터를 저장 하는 응용 프로그램 `TableAdapter`s를 사용 하 여 쿼리를 실행 하는 응용 프로그램 엔터티의 데이터를 저장 하는 반면 [LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d) 또는 엔터티를 연결 하 여 에 직접 저장된 프로시저입니다. Tableadapter를 사용 하는 쿼리 만들기 및 편집 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md) 하 고 [방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)합니다.  
  
 데이터 집합에 데이터 로드 및 쿼리 및 저장된 프로시저를 실행 하는 방법에 대 한 자세한 내용은 참조 하세요 [응용 프로그램에 데이터를 가져오는](../data-tools/fetching-data-into-your-application.md)합니다.  
  
 데이터 집합에 데이터를 로드 하는 방법에 알아보려면의 절차를 완료 [연습: Windows Form에서 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md) 폼 로드 이벤트 처리기에서 코드를 검사 합니다.  
  
 데이터를 로드 하는 방법을 알아보려면 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 의 절차를 완료 하는 개체를 [연습: 만들기 LINQ to SQL 클래스 (O-r 디자이너)](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)합니다.  
  
 참조를 만들고 SQL 쿼리를 실행 하는 방법을 알아보려면 [방법: 만들고 행을 반환 하는 SQL 문을 실행](http://msdn.microsoft.com/library/14637fc5-d42a-4cca-97ac-54c181ec3eed)합니다.  
  
 저장된 프로시저를 실행 하는 방법에 알아보려면 참조 [방법: 저장 프로시저는 반환 행 실행](http://msdn.microsoft.com/library/db3d7021-d3ef-4db8-b12a-b6146570355d)합니다.  
  
## <a name="displaying-data-on-forms"></a>폼에서 데이터 표시  
 응용 프로그램에 데이터를 바인딩한 이후에는 일반적으로 폼에 데이터를 표시하여 사용자가 데이터를 보거나 수정할 수 있게 합니다. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 제공 된 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)폼 데이터를 표시 하는 데이터 바인딩된 컨트롤을 자동으로 만들려면 항목을 이동할 수 있는, 합니다. 데이터 바인딩 및 사용자에 게 데이터를 표시에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다.  
  
 사용자에 게 데이터를 제공 하는 방법에 알아보려면 다음 연습에 나오는 절차를 완료 (에서 항목을 끌어 오는 프로세스에 특히 주의 합니다 **데이터 원본** 창).  
  
-   [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)합니다.  
  
-   [WCF 데이터 서비스에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)  
  
-   [연습: WCF 데이터 서비스로 Silverlight 컨트롤 바인딩](http://msdn.microsoft.com/library/f3f08661-7d91-4185-8ed6-912d524d4c6b)  
  
## <a name="editing-data-in-your-application"></a>응용 프로그램에서 데이터 편집  
 사용자에게 데이터를 표시하면 사용자는 데이터를 다시 데이터베이스로 전송하기 전에 새 레코드를 추가하고 레코드를 편집 및 삭제하는 수정 작업을 하는 경우가 많습니다.  
  
 데이터 집합에 로드 되 면 작업 데이터에 대 한 자세한 내용은 참조 하세요. [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)합니다.  
  
## <a name="validating-data"></a>데이터 유효성 검사  
 데이터를 변경할 때는 값이 데이터 집합에 적용되거나 데이터베이스에 기록되기 전에 변경 내용을 확인하는 것이 좋습니다. *유효성 검사* 이러한 새 값이 응용 프로그램의 요구 사항에 부합 하는지 확인 하는 것에 대 한 프로세스의 이름입니다. 응용 프로그램에서 값이 변경될 때 해당 값을 확인하는 논리를 추가할 수 있습니다. Visual Studio는 열 및 행 변경 시 데이터 유효성을 검증하는 코드를 쉽게 추가할 수 있는 도구를 제공합니다. 자세한 내용은 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)합니다.  
  
 응용 프로그램에 데이터 유효성 검사를 추가 하는 방법에 알아보려면 참조 [연습: 데이터 집합에 유효성 검사 추가](http://msdn.microsoft.com/library/09351fab-d670-45e3-b53a-a944eff717e7)합니다.  
  
 N 계층 응용 프로그램으로 분리 되어 있는 데이터 집합에 유효성 검사를 추가 하는 방법에 알아보려면 참조 [n 계층 데이터 집합에 유효성 검사 추가](../data-tools/add-validation-to-an-n-tier-dataset.md)합니다.  
  
## <a name="saving-data"></a>데이터 저장  
 응용 프로그램에서 변경 작업을 하고 해당 변경 내용의 유효성을 검사한 다음에는 일반적으로 변경 내용을 다시 데이터베이스로 보냅니다. 데이터 집합에 데이터를 저장하는 응용 프로그램은 일반적으로 TableAdapterManager를 사용하여 데이터를 저장합니다. 자세한 내용은 [TableAdapterManager 개요](http://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)합니다. Entity Framework 응용 프로그램 사용을 <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> 데이터를 저장 하는 방법입니다.  
  
 업데이트 된 데이터를 데이터베이스로 다시 보내는 방법에 대 한 자세한 내용은 참조 하세요. [데이터 저장](../data-tools/saving-data.md)합니다.  
  
 데이터베이스에 데이터 집합에서 업데이트 된 데이터를 보내는 방법에 알아보려면의 절차를 완료 [연습: 관련 데이터 테이블 (계층적 업데이트)에서 데이터 저장](http://msdn.microsoft.com/library/50601bd7-a488-480c-9910-3c6570fa3a1b)합니다.  
  
## <a name="related-topics"></a>관련 항목  
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)  
 데이터를 다루는 응용 프로그램을 만드는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)  
 사용 하는 방법에 대 한 항목에 대 한 링크를 제공 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 응용 프로그램을 데이터를 연결 하 고 응용 프로그램에 대 한 데이터 원본을 만들어야 합니다.  
  
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)  
 응용 프로그램에서 데이터 집합 및 엔터티 데이터 모델 등의 데이터 모델을 사용하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)  
 데이터를 응용 프로그램으로 로드하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)  
 Windows Forms 컨트롤, WPF 컨트롤 및 Silverlight 컨트롤을 데이터 소스에 바인딩하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)  
 응용 프로그램에서 데이터를 변경하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 데이터 변경 내용의 유효성 검사를 추가하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [데이터 저장](../data-tools/saving-data.md)  
 응용 프로그램에서 업데이트한 데이터를 데이터베이스로 보내는 방법 또는 업데이트한 데이터를 XML 등의 다른 형식으로 저장하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [Visual Studio에서 데이터 원본을 사용 하기 위한 도구](http://msdn.microsoft.com/library/1e584c75-900a-49a0-a82a-d19172ef2eb3)  
 와 같은 Visual Studio에서 데이터 원본으로 작업 하는 데 사용할 수 있는 도구에 대 한 항목에 대 한 링크를 제공 합니다 **데이터 원본** 창 및 ADO.NET 엔터티 데이터 모델 디자이너.