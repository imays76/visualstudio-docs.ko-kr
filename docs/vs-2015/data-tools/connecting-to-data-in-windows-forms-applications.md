---
title: Forms 응용 프로그램을 Windows에는 데이터에 연결 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- System.Data.SqlClient.SqlConnection
- System.Data.Odbc.OdbcConnection
- System.Data.OleDb.OleDbConnection
- System.Data.OracleClient.OracleConnection
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- connection objects, tools for working with
- OleDbConnection class, ADO.NET connection objects
- databases [Visual Studio], connecting to
- data adapters, connections
- connection pooling, ADO.NET connections
- connection strings [Visual Studio], ADO.NET
- connection objects, types of
- dynamic properties, ADO.NET connections
- connections, about connections
- data [Visual Studio], connecting
- design-time connections
- connections, design-time
- TableAdapters, connections
- connection objects
- SqlConnection class, ADO.NET connection objects
- connecting to databases, ADO.NET connections
- transactions, ADO.NET
- database connections [Visual Studio], ADO.NET
ms.assetid: 184cbd0d-3b26-418d-a11c-f9f8f004fbff
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: d8da35b32f3dd25bd7ed47b25f722c6b0aa21ac7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208951"
---
# <a name="connecting-to-data-in-windows-forms-applications"></a>Windows Forms 응용 프로그램에서 데이터에 연결
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서는 데이터베이스, 웹 서비스, 개체 등 서로 다른 여러 소스의 데이터에 응용 프로그램을 연결하는 도구를 제공합니다. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 데이터 디자인 도구를 사용하는 경우에는 폼이나 구성 요소에 대해 연결 개체를 명시적으로 만들지 않아도 되는 경우가 많습니다. 연결 개체는 대개 데이터 마법사 중 하나를 완료하거나 데이터 개체를 폼으로 끌어옴으로써 만들어집니다. 응용 프로그램을 데이터베이스, 웹 서비스 또는 개체의 데이터에 연결 하려면 다음을 실행 합니다 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f) 를 선택 하 여 **새 데이터 소스 추가** 에서 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
 다음 다이어그램에는 TableAdapter 쿼리를 실행하여 데이터에 연결해 데이터를 가져온 다음 Windows 응용 프로그램의 폼에 표시할 때의 표준 작업 흐름이 나와 있습니다.  
  
 ![클라이언트 응용 프로그램에서 데이터 흐름](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")  
  
 데이터 디자인 도구를 사용하지 않고 연결 개체를 만드는 것이 편리한 경우도 있습니다. 프로그래밍 방식으로 연결을 만드는 방법은 [데이터 원본에 연결할](http://msdn.microsoft.com/library/9abc3f92-1be3-4e1a-b360-762dc689650e)합니다.  
  
> [!NOTE]
>  웹 응용 프로그램을 데이터를 연결 하는 방법에 대 한 정보를 참조 하세요 [ASP.NET 데이터 액세스 콘텐츠 맵](http://msdn.microsoft.com/en-us/f9219396-a0fa-481f-894d-e3d9c67d64f2)합니다.  
  
## <a name="walkthroughs-for-connecting-windows-forms-applications-to-data"></a>Windows Forms 응용 프로그램을 데이터에 연결하는 연습  
 다음 연습에서는 Windows Forms 응용 프로그램의 데이터에 연결하는 작업과 관련된 절차를 제공합니다.  
  
-   [연습: 데이터에에서 연결 하는 데이터베이스 (Windows Forms)](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)  
  
-   [연습: 로컬 데이터베이스 파일의 데이터에 연결(Windows Forms)](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)  
  
-   [연습: 데이터에에서 연결 하는 웹 서비스 (Windows Forms)](http://msdn.microsoft.com/library/079fb9b0-c733-40c1-acd1-d0d68834354d)  
  
-   [연습: 데이터에에서 연결 개체 (Windows Forms)](http://msdn.microsoft.com/library/21a7fba2-b38b-4726-8cbe-d22154b75a05)  
  
-   [Access 데이터베이스의 데이터에 연결(Windows Forms)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)  
  
## <a name="creating-connections"></a>연결 만들기  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]를 사용 하 여 연결을 구성 합니다 **연결 추가/수정** 대화 상자. 합니다 **연결 추가** 대화 상자가 나타나면 편집 하거나 데이터 마법사 중 하나에서 연결을 만들 때 또는 [서버 탐색기/데이터베이스 탐색기](http://msdn.microsoft.com/library/4ea29b3b-bbb2-45e4-9082-eaf635c41c4d) 에서 연결 속성을 편집 하는 경우 또는 합니다 **속성** 창입니다.  
  
 다음 작업 중 하나를 수행할 때는 데이터 연결이 자동으로 구성됩니다.  
  
|동작|설명|  
|------------|-----------------|  
|실행 합니다 [데이터 원본 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)합니다.|데이터베이스 경로 선택 하면 연결을 구성 합니다 **데이터 소스 구성 마법사**합니다. 자세한 내용은 [How to: Connect to Data in a Database](../data-tools/how-to-connect-to-data-in-a-database.md)을 참조하십시오.|  
|실행 합니다 [TableAdapter 구성 마법사](http://msdn.microsoft.com/library/3a373dd9-7b34-4d3c-a48b-69414512bac8)합니다.|내에서 연결이 만들어집니다 합니다 **TableAdapter 구성 마법사**합니다. 자세한 내용은 [만들기 및 Tableadapter 구성](../data-tools/create-and-configure-tableadapters.md)합니다.|  
|실행 합니다 [Tableadapter 편집](../data-tools/editing-tableadapters.md)합니다.|내에서 연결이 만들어집니다 합니다 **TableAdapter 쿼리 구성 마법사**합니다. 자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)합니다.|  
|항목을 끌어 합니다 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) 폼 또는 [구성 요소 디자이너](http://msdn.microsoft.com/library/61a3a450-5b15-465e-bd9a-72a6c8c2b282)합니다.|연결 개체에서 항목을 끌면 만들어집니다 합니다 **데이터 원본** 창만 **Windows Forms 디자이너** 또는 **구성 요소 디자이너**합니다. 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다.|  
|새 데이터 연결을 추가 [서버 탐색기/데이터베이스 탐색기](http://msdn.microsoft.com/library/4ea29b3b-bbb2-45e4-9082-eaf635c41c4d)합니다.|데이터 연결 **서버 탐색기/데이터베이스 탐색기** 데이터 마법사 내의 사용 가능한 연결 목록에 표시|  
  
## <a name="connection-strings"></a>연결 문자열  
 컴파일된 응용 프로그램 또는 응용 프로그램 구성 파일 내에 연결 문자열을 저장할 수 있습니다. 자세한 내용은 [방법: 저장 및 연결 문자열 편집](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)합니다.  
  
## <a name="connection-information-and-security"></a>연결 정보 및 보안  
 연결을 열 때는 중요한 리소스인 데이터베이스에 액세스하므로 연결 구성 및 사용과 관련된 보안 문제가 흔히 발생합니다.  
  
 시스템의 아키텍처에 따라 응용 프로그램 및 응용 프로그램의 데이터 소스 액세스를 보호하는 방법이 결정됩니다. 예를 들어 웹 기반 응용 프로그램에서는 사용자가 보통 IIS(인터넷 정보 서비스)에 익명으로 액세스하므로 보안 자격 증명을 제공하지 않습니다. 이 경우 응용 프로그램이 특정 사용자 정보 대신 자체 로그온 정보를 유지 관리하며 연결을 열고 데이터베이스에 액세스하는 데 해당 정보를 사용합니다.  
  
> [!IMPORTANT]
>  암호와 같은 연결 문자열 세부 정보를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 Windows 통합 보안을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](http://msdn.microsoft.com/library/1471f580-bcd4-4046-bdaf-d2541ecda2f4)를 참조하세요.  
  
 인트라넷 또는 다층 계층 응용 프로그램에서는 Windows, IIS 및 SQL Server에서 제공하는 통합 보안 옵션을 활용할 수 있습니다. 이 모델에서는 데이터베이스 리소스에 액세스하는 데 로컬 네트워크용 사용자 인증 자격 증명도 사용할 수 있으며 연결 문자열에 명시적인 사용자 이름 또는 암호가 사용되지 않습니다. 일반적으로는 그룹을 통해 데이터베이스 서버 컴퓨터에서 사용 권한이 설정되므로 데이터베이스에 액세스할 수 있는 모든 사용자에 대해 개별 사용 권한을 설정하지 않아도 됩니다. 이 모델에서는 연결에 대해 로그온 정보 자체를 저장할 필요가 없으며 연결 문자열 정보를 보호하기 위해 수행해야 하는 추가 단계도 없습니다.  
  
 보안에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [ADO.NET 응용 프로그램 보안](http://msdn.microsoft.com/library/005a1d43-6ee5-471e-ad98-1d30a44d49d5)  
  
-   [Windows Forms의 파일 및 데이터 액세스 추가 보안](http://msdn.microsoft.com/library/3cd3e55b-2f5e-40dd-835d-f50f7ce08967)  
  
## <a name="design-time-connections-in-server-explorerdatabase-explorer"></a>서버 탐색기/데이터베이스 탐색기의 디자인 타임 연결  
 **서버 탐색기/데이터베이스 탐색기** 디자인 타임 데이터 원본 연결을 만들 수 있는 방법을 제공 합니다. 그러면 사용 가능한 데이터 소스를 찾아보고, 데이터 소스에 포함된 테이블, 열 및 기타 요소에 대한 정보를 표시하고, 데이터베이스 요소를 편집/작성할 수 있습니다.  
  
 응용 프로그램에서 사용할 수 있는 연결을 직접 사용 되지 않는 **서버 탐색기/데이터베이스 탐색기**합니다. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서는 이러한 연결을 통해 디자인 타임에 데이터베이스를 사용합니다. 자세한 내용은 [Visual Database Tools](http://msdn.microsoft.com/en-us/6b145922-2f00-47db-befc-bf351b4809a1)합니다.  
  
 예를 들어 디자인 타임에 사용할 수 있습니다 **서버 탐색기/데이터베이스 탐색기** 데이터베이스로 연결을 만듭니다. 나중에 폼을 디자인할 때 데이터베이스를 이동, 테이블에서 열을 선택 하 수 끌어 합니다 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md)합니다. 이렇게 한 [TableAdapter](../data-tools/tableadapter-overview.md) 데이터 집합에 있습니다. 또한 새로 만들어진 TableAdapter의 일부분인 새 연결 개체도 만들어집니다.  
  
 디자인 타임 연결에 대한 정보는 특정 프로젝트나 솔루션과는 독립적으로 로컬 컴퓨터에 저장됩니다. 따라서 응용 프로그램에서 작업 하는 동안 디자인 타임 연결을 설정한 후에 나타나도록 **서버 탐색기/데이터베이스 탐색기** 에서 작업할 때마다 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], 서버를 오랫동안 연결 요소를 사용할 수 있습니다. 자세한 내용은 [방법: 서버 탐색기에서 데이터베이스를 연결할](http://msdn.microsoft.com/en-us/7c1c3067-0d77-471b-872b-639f9f50db74)합니다.  
  
 [!INCLUDE[SQLObjectExplorer](../includes/sqlobjectexplorer-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [연습: 데이터에에서 연결 하는 데이터베이스 (Windows Forms)](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)   
 [ASP.NET 데이터 액세스 콘텐츠 맵](http://msdn.microsoft.com/en-us/f9219396-a0fa-481f-894d-e3d9c67d64f2)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)