---
title: 로컬 데이터 개요 | Microsoft Docs
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
- SQL Server Express
- local data
- SQL Server LocalDB
- LocalDB
- SQLEXPRESS
- SQL Server, local data
- SQL Express
- SQL Server Compact
- data access [Visual Studio], troubleshooting
- Access, .mdb files in Visual Studio
- data [Visual Studio], local
ms.assetid: d6afa5ac-2bb8-49f2-a50e-f71f611ed506
caps.latest.revision: 71
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 94b3f066a66a380875609b4f6485d56a19ebde3e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49885579"
---
# <a name="local-data-overview"></a>로컬 데이터 개요
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

데이터 응용 프로그램을 개발할 때 데이터베이스의 로컬 복사본을 사용 하는 것이 좋습니다 프로덕션 데이터에 오류가 발생 하지 않도록 합니다. 도 테스트 데이터베이스를 다른 개발자와 공유 검색 하드 방식에서 상호 작용 하는 오류를 초래 하는 두 명의 개발자 경우 잠재적인 문제를 만듭니다. 로컬 컴퓨터의 고유한 테스트 데이터를 사용 하 여 이러한 모든 문제를 방지할 수 있습니다. 대부분 경우 일부 데이터베이스 시스템을 사용 하면 로컬 데이터 파일을 만들 수 있습니다. .NET 프로젝트에 대 한 Visual Studio는 로컬 SQL Server 데이터베이스 파일 (.mdf) 및 Microsoft Access 데이터베이스 파일 (.mdb)에 대 한 특별 한 지원을 제공 합니다.  
  
 Visual Studio에서는 이러한 시나리오를 지원합니다.  
  
1.  
  
2.  
  
- 
  
- 
  
- 솔루션 탐색기에서 솔루션 노드를 클릭 하 고 선택 하 여 SQL Server 데이터베이스 프로젝트를 만듭니다 **추가 &#124; 새 프로젝트**합니다.  왼쪽된 창에서 선택 **SQL Server &#124; 데이터베이스** 프로젝트 및 확인을 클릭 합니다. 솔루션 탐색기에서 로컬 데이터베이스 파일을 가져오려면 데이터베이스 프로젝트 노드를 마우스 오른쪽 단추로 클릭 한 다음 프로젝트에서 생성 한 데이터베이스에 연결 하는 응용 프로그램을 개발 합니다. 개발 하 고 동시에 응용 프로그램을 개발 하는 경우 데이터베이스 스키마를 수정 하는 경우 적합 합니다.  
  
   ![데이터베이스를 데이터베이스 프로젝트로 가져올](../data-tools/media/raddata-import-database-into-database-project.png "데이터베이스 프로젝트로 raddata 데이터베이스 가져오기")  
  
- 새 데이터베이스를 만드는 경우 먼저 추가 된 **서비스 기반 데이터베이스 파일** 프로젝트 (**프로젝트 &#124; 새 항목 추가)** 합니다. 이 기본적으로 (localdb) \MSSQLocalDB 로컬 컴퓨터에서 기본 SQL Server 인스턴스에 연결 된 새.mdf 파일을 만듭니다. 데이터베이스 서버 탐색기에 표시 됩니다. 노드를 확장 하 고 테이블, 뷰, 함수 등 새 데이터베이스 개체를 추가할 노드를 마우스 오른쪽 단추로 클릭 합니다.  
  
  SQL Server Express LocalDB에 대 한 자세한 내용은 참조 하세요. [Introducing LocalDB, an Improved SQL Express](http://go.microsoft.com/fwlink/?LinkId=234375) 하 고 [LocalDB: Where is My Database?](http://go.microsoft.com/fwlink/?LinkId=234376) Microsoft 웹 사이트입니다.  
  
  다음 표에서는 응용 프로그램을 로컬 데이터에 연결하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
|항목|설명|  
|-----------|-----------------|  
|[디자이너를 사용하여 SQL 데이터베이스 만들기](../data-tools/create-a-sql-database-by-using-a-designer.md)|데이터 기능을 테스트하고 응용 프로그램을 빌드하는 데 사용할 수 있는 로컬 데이터베이스 파일을 만들기 위한 단계별 지침을 제공합니다.|  
|[연습: 로컬 데이터베이스 파일의 데이터에 연결(Windows Forms)](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)|간단한 Windows 응용 프로그램을 만드는 동안 SQL Server Express LocalDB 데이터베이스에 연결하기 위한 단계별 지침을 제공합니다.|  
|[Access 데이터베이스의 데이터에 연결(Windows Forms)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)|Microsoft Access 데이터베이스에 연결하기 위한 단계별 지침을 제공합니다.|  
|[방법: Northwind 데이터베이스에 연결](../data-tools/how-to-connect-to-the-northwind-database.md)|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], SQL Server Compact, SQL Server Express 및 Access에서 Northwind 샘플 데이터베이스에 연결하기 위한 지침을 제공합니다.|  
  
## <a name="use-the-connection-string"></a>연결 문자열 사용  
 간단 하 게 이며 응용 프로그램 데이터베이스에서 읽기만 하는 경우 및 타사 데이터베이스를 사용 하는 경우 적합 한 선택입니다. 데이터베이스 파일을 로컬 컴퓨터에서 응용 프로그램에 액세스 하려면 권한이 있는 데이터베이스 시스템에서 지 원하는 모든 위치에 수 있습니다.  
  
1.  (선택 사항) 에 설명 된 대로 새 연결을 만듭니다 [새 연결 추가](../data-tools/add-new-connections.md)합니다. 타사 데이터베이스와는 이미 연결 문자열을 알고와 됩니다 하지 수 데이터 바인딩 수행 또는 Entity Framework 클래스 또는 데이터 집합과 같은 데이터 소스를 사용 하 여.mdf 파일에 대 한이 단계가 필요 하지 않습니다. 로컬 파일에 연결할 연결 문자열을 사용 합니다. .Mdf 파일을 참조 하세요 [.mdf 파일 업그레이드](../data-tools/upgrade-dot-mdf-files.md) 하 고 [연결을 설정할](https://msdn.microsoft.com/en-us/library/ms254507.aspx)합니다.  
  
2.  (선택 사항) Entity Framework 또는 LINQ to SQL 데이터 집합을 사용 하는 경우 데이터 소스 구성 마법사를 사용 하 여 데이터 원본을 만듭니다. 자세한 내용은 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)를 참조하세요.  
  
## <a name="add-an-existing-mdf-to-your-project"></a>프로젝트에 기존.mdf 추가  
 응용 프로그램은 수 삽입, 삭제 또는 업데이트할 데이터를 사용할 수 있는 원본 파일의 복사본을 유지 하려는 경우는 것이 좋습니다 프로젝트 파일에 추가 합니다. 이렇게 할 때를 항목 속성을 설정할 수 있습니다 **출력 디렉터리로 복사** 하 **항상 복사** 또는 **변경 된 내용만 복사**, 및 응용 프로그램을 개발 합니다. 응용 프로그램을 빌드할 때마다 출력 폴더로 복사 됩니다 원본 데이터베이스 및 응용 프로그램의 변경 내용이 복사본에 대해 수행 합니다. 이렇게 하면 항상 없습니다 원래 데이터의 새로 복사 합니다.  
  
1.  사용 하 여 **Windows 파일 탐색기** 끌어서 Visual Studio의 솔루션 탐색기에서 프로젝트 노드를 현재 위치에서.mdf 파일을 삭제 합니다.  파일은 이미에 연결 된 localDB 인스턴스를 먼저 분리 해야 합니다. 프로젝트에 삭제 한 후 Visual Studio는 자동으로 다시 연결할 기본 localDB 인스턴스.  
  
2.  새 데이터베이스 노드 단추로 클릭 하 고 속성을 선택 합니다. 복사 동작을 선택할 **항상 복사** 하거나 **변경 된 내용만 복사**합니다.  
  
## <a name="create-a-sql-server-database-project-and-import-your-database"></a>SQL Server 데이터베이스 프로젝트를 만들고 데이터베이스 가져오기  
 개발할은 데이터베이스 자체 아마도 열 또는 테이블을 추가 하거나 데이터 형식을 변경 하는 경우 좋은 옵션입니다.  
  
## <a name="each-project-contains-two-copies-of-the-database"></a>각 프로젝트에 두 개의 데이터베이스 복사본 포함  
 출력에 루트 프로젝트 폴더에서 데이터베이스 파일이 복사 됩니다는 프로젝트를 빌드하면 **bin**, 폴더입니다. 이 동작에 따라 달라 집니다 합니다 **출력 디렉터리로 복사** 파일의 속성과 해당 속성의 기본값을 사용 하는 데이터베이스 파일의 유형에 따라 다릅니다.  
  
 보려는 **bin** 폴더에 **솔루션 탐색기**를 선택 합니다 **모든 파일 표시** 도구 모음에서.  
  
> [!NOTE]
>  합니다 **출력 디렉터리로 복사** 속성 웹 또는 c + + 프로젝트에 적용 되지 않습니다.  
  
 루트 프로젝트 폴더에 데이터베이스 파일을 사용 하 여 데이터베이스 스키마 나 데이터를 편집 하는 경우에 변경 **서버 탐색기**/**데이터베이스 탐색기** 또는 기타 [Visual 데이터베이스 도구](http://msdn.microsoft.com/en-us/6b145922-2f00-47db-befc-bf351b4809a1)합니다.  
  
 데이터베이스를 변경 하는 응용 프로그램을 개발 하는 동안 데이터를 변경 합니다 **bin** 폴더입니다. 예를 들어, F5 키를 선택하여 응용 프로그램을 디버그하는 경우 해당 폴더의 데이터베이스에 연결됩니다.  
  
|값 **출력 디렉터리로 복사** 속성|동작|  
|----------------------------------------------------|--------------|  
|**변경 된 내용만 복사** (.sdf 파일에 대 한 값을 기본값)|데이터베이스 파일은 프로젝트 디렉터리에서 복사 합니다 **bin** 처음으로 프로젝트를 빌드할 때 디렉터리입니다. 합니다 **수정한 날짜** 속성 파일의 프로젝트를 다시 빌드할 때마다 비교 됩니다. 프로젝트 폴더에서 파일이 최신 파일인 경우 복사 합니다 **bin** 폴더를 이전 파일을 대체 합니다. 새 버전이 아니면 파일이 복사되지 않습니다. **주의:** .mdb 또는.mdf 파일에 대 한이 값이 권장 되지 않습니다. 데이터가 변경되지 않아도 데이터베이스 파일은 변경될 수 있습니다. 파일 연결을 열기만 해도 새 버전으로 표시 될 수 있습니다 (예를 들어, 확장 된 **테이블** 노드에서 **서버 탐색기**).|  
|**항상 복사** (기본값.mdf 및.mdb 파일)|데이터베이스 파일은 프로젝트 디렉터리에서 복사 합니다 **bin** 응용 프로그램을 빌드할 때마다 디렉터리입니다. 다음에 응용 프로그램을 실행할 때 출력 폴더의 데이터 파일에 대해 변경된 모든 내용을 덮어씁니다.|  
|**복사 안 함**|시스템에서 파일을 덮어쓰지 않습니다 합니다 **bin** 디렉터리입니다. 응용 프로그램에서 출력 디렉터리에 있는 데이터베이스 파일을 가리키는 동적 연결 문자열을 만듭니다. 따라서 출력 디렉터리의 데이터가 프로젝트 디렉터리의 데이터와 일치하도록 하려면 파일을 출력 디렉터리로 직접 복사해야 합니다.|  
  
## <a name="common-issues-with-local-data"></a>일반적인 로컬 데이터 문제  
 다음 표에서는 로컬 데이터 파일에 대한 작업을 수행하는 동안 발생하는 일반적인 문제에 대해 설명합니다.  
  
|문제|설명|  
|-----------|-----------------|  
|응용 프로그램을 테스트하고 데이터를 수정해도 다음에 응용 프로그램을 실행하면 변경 내용이 사라집니다.|값을 **출력 디렉터리로 복사** 속성은 **변경 된 내용만 복사** 또는 **항상 복사**합니다. 프로젝트를 빌드할 때마다 출력 폴더에 있는 데이터베이스(응용 프로그램을 테스트할 때 수정되는 데이터베이스)를 덮어씁니다. 자세한 내용은 [방법: 프로젝트의 로컬 데이터 파일 관리](../data-tools/how-to-manage-local-data-files-in-your-project.md)합니다.|  
|데이터 파일이 잠겨 있다는 내용의 메시지가 표시됩니다.|Access(.mdb 파일): 파일이 Access와 같은 다른 프로그램에서 열려 있지 않은지 확인합니다.<br /><br /> SQL Server Express(.mdf 파일): Visual Studio IDE 외부에서 데이터 파일을 복사, 이동 또는 이름을 바꾸는 경우 SQL Express에서 해당 데이터 파일을 잠급니다.|  
|두 명 이상의 사용자가 동시에 같은 데이터베이스에 액세스하려고 하면 액세스가 거부됩니다.|Visual Studio 활용 *사용자 인스턴스*, 각 사용자에 대 한 SQL Server의 별도 인스턴스를 만드는 SQL Server Express의 기능인 합니다. 한 사용자가 파일에 액세스하면 그 다음 사용자는 해당 파일에 연결할 수 없습니다. 이 문제는 예를 들어 사용자가 ASP.NET Development Server와 IIS(인터넷 정보 서비스)에서 웹 응용 프로그램을 동시에 실행하려고 할 때 발생할 수 있습니다. IIS는 일반적으로 다른 계정으로 실행해야 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [연습: 데이터에에서 연결 하는 로컬 데이터베이스 파일 (Windows Forms)](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)   
 [Access 데이터베이스의 데이터에 연결(Windows Forms)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)