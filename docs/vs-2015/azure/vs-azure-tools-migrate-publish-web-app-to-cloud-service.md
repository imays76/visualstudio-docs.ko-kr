---
title: 마이그레이션 및 Visual Studio에서 Azure 클라우드 서비스에 웹 응용 프로그램을 게시 하는 방법 | Microsoft Docs
description: 마이그레이션 및 Visual Studio를 사용 하 여 Azure cloud service에 웹 응용 프로그램을 게시 하는 방법을 알아봅니다
author: ghogen
manager: douge
ms.assetid: 9394adfd-a645-4664-9354-dd5df08e8c91
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/10/2017
ms.author: ghogen
ms.openlocfilehash: c122b54a4e22285678d13213cc73d6492baba629
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51003043"
---
# <a name="how-to-migrate-and-publish-a-web-application-to-an-azure-cloud-service-from-visual-studio"></a>방법: 마이그레이션 및 Visual Studio에서 Azure 클라우드 서비스에 웹 응용 프로그램 게시

호스팅 서비스를 활용 하 고 Azure의 확장 기능을 사용 하려면 마이그레이션할 Azure cloud service에 웹 응용 프로그램을 배포 하는 것이 좋습니다. 최소한의 변경만 않아도 됩니다. 이 문서에서는 클라우드 서비스에만; 배포 App Service에 대 한 참조 [Azure App Service에서 웹 앱 배포](/azure/app-service/app-service-deploy-local-git)합니다.

> [!Important]
> 이 마이그레이션은 특정 ASP.NET, Silverlight, WCF 및 WCF 워크플로 프로젝트에 대해서만 지원 됩니다. ASP.NET Core 프로젝트는 지원 되지 않습니다. 참조 [지원 되는 프로젝트 템플릿](#supported-project-templates)합니다.

## <a name="migrate-a-project-to-cloud-services"></a>클라우드 서비스에 프로젝트 마이그레이션

1. 웹 응용 프로그램 프로젝트를 마우스 오른쪽 단추로 누르고 **변환 > Microsoft Azure 클라우드 서비스 프로젝트로 변환**합니다. (솔루션의 웹 역할 프로젝트를 이미 있는 경우이 명령이 나타나지 않으면 note 합니다.)
1. Visual Studio 솔루션에 필요한 웹 역할을 포함 하는 클라우드 서비스 프로젝트를 만듭니다. 이 프로젝트의 이름이 동일한 응용 프로그램 프로젝트와 접미사 `.Azure`합니다.
1. Visual Studio 설정 합니다 **복사 로컬** 속성을 true로 MVC 2, MVC 3, MVC 4 및 Silverlight 비즈니스 응용 프로그램에 필요한 모든 어셈블리에 대 한 합니다. 이 속성은 배포에 사용 되는 서비스 패키지에 이러한 어셈블리를 추가 합니다.

   > [!Important]
   > 다른 어셈블리 또는 파일이이 웹 응용 프로그램에 필요한 경우 이러한 파일에 대 한 속성을 수동으로 설정 해야 합니다. 이러한 속성을 설정 하는 방법에 대 한 정보를 참조 하세요 [서비스 패키지에 파일 포함](#include-files-in-the-service-package)합니다.

### <a name="errors-and-warnings"></a>오류 및 경고

모든 경고 또는 오류가 발생 하는 어셈블리 누락 처럼 azure에 배포 하기 전에 해결할 문제를 나타냅니다.

응용 프로그램을 빌드, 계산 에뮬레이터를 사용 하 여 로컬로 실행 또는 Azure에 게시 하는 경우 오류가 표시 될 수 있습니다. "지정된 된 경로, 파일 이름 또는 둘 다가 너무 깁니다." 이 오류는 정규화 된 Azure 프로젝트 이름의 길이는 146 자를 초과 하는 나타냅니다. 문제를 해결 하려면 솔루션을 더 짧은 경로 사용 하 여 다른 폴더로 이동 합니다.

모든 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하세요. [Visual Studio를 사용 하 여 Azure 클라우드 서비스 프로젝트를 구성](vs-azure-tools-configuring-an-azure-project.md)합니다.

### <a name="test-the-migration-locally"></a>로컬로 마이그레이션 테스트

1. Visual Studio에서 **솔루션 탐색기**, 추가 클라우드 서비스 프로젝트를 마우스 오른쪽 단추로 **시작 프로젝트로 설정**합니다.
1. 선택 **디버그 > 디버깅 시작** Azure 디버깅 환경 시작 (F5). 이 환경은 다양 한 Azure 서비스의 에뮬레이션을 제공 합니다.

### <a name="use-an-azure-sql-database-for-your-application"></a>Azure SQL Database를 사용 하 여 응용 프로그램에 대 한

온-프레미스 SQL Server 데이터베이스를 사용 하는 웹 응용 프로그램에 대 한 연결 문자열이 있는 경우 대신 Azure SQL Database로 데이터베이스를 마이그레이션 하 고 연결 문자열 업데이트 해야 합니다. 이 프로세스를 사용 하 여 지침을 보려면 다음 항목을 참조 하세요.

- [클라우드에서 SQL Database로 SQL Server 데이터베이스 마이그레이션](/azure/sql-database/sql-database-cloud-migrate)
- [.NET을 사용 하 여 (C#) 연결 및 쿼리 하는 Visual Studio 및 Azure SQL database를 사용 하 여](/azure/sql-database/sql-database-connect-query-dotnet-visual-studio)합니다.

## <a name="publish-the-application-to-azure-cloud-service"></a>Azure Cloud Service에 응용 프로그램 게시

1. 필요한 클라우드 서비스 및 저장소 계정을 만들 Azure 구독에서에 설명 된 대로 [Visual Studio에서 Azure 응용 프로그램 배포 또는 게시 준비](vs-azure-tools-cloud-service-publish-set-up-required-services-in-visual-studio.md)합니다.
1. Visual Studio에서 응용 프로그램 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **Microsoft Azure에 게시 하는 중...**  (하는 "게시..." 명령과 다릅니다.).
1. 에 **Azure 응용 프로그램 게시** 선택한 Azure 구독 계정을 사용 하 여 로그인 나타나는 **다음 >** 합니다.
1. 에 **설정 > 일반 설정** 탭에서 대상 클라우드 서비스를 선택 합니다 합니다 **클라우드 서비스** 선택한 환경 및 구성을 함께 드롭 다운 목록. 
1. **설정 > 고급 설정**, 클릭을 사용 하려면 저장소 계정 선택 **다음 >** 합니다.
1. **진단**, Application Insights에 정보를 보낼지 여부를 선택 합니다.
1. 선택 **다음 >** 요약을 보려면 클릭 **게시** 배포를 시작 합니다.
1. Visual Studio에는 진행률을 추적할 수 있는 활동 로그 창이 열립니다.

    ![VST_AzureActivityLog](./media/vs-azure-tools-migrate-publish-web-app-to-cloud-service/IC744149.png)

1. (선택 사항) 배포 프로세스를 취소 하려면 활동 로그에서 품목을 마우스 오른쪽 단추로 클릭 하 고 선택 **취소 및 제거**합니다. 이 명령은 배포 프로세스를 중지 하 고 Azure에서 배포 환경이 삭제 합니다. 참고:이 배포 환경을 배포한 후 제거를 사용 해야 합니다는 [Azure portal](https://portal.azure.com)합니다.
1. (선택 사항) Visual Studio 배포 환경을 자동으로 표시 역할 인스턴스가 시작 된 후에 **서버 탐색기 > Cloud Services** 노드. 여기에서 개별 역할 인스턴스의 상태를 볼 수 있습니다.
1. 배포 후 응용 프로그램에 액세스 하려면 상태의 때 배포 옆의 화살표를 선택 **완료 됨** 에 표시 되는 **Azure 활동 로그** URL과 함께 합니다. Azure에서 특정 유형의 웹 응용 프로그램을 시작 하는 방법에 대 한 자세한 내용은 다음 표를 참조 하세요.

## <a name="using-the-compute-emulator-and-starting-application-in-azure"></a>계산 에뮬레이터를 사용 하 고 Azure에서 응용 프로그램을 시작 합니다.

모든 응용 프로그램 종류를 선택 하 여 Visual Studio 디버거를 연결할 브라우저에서 시작할 수 있습니다 **디버그 > 디버깅 시작** (F5). ASP.NET 빈 웹 응용 프로그램 프로젝트를 사용 하 여 먼저 추가 해야는 `.aspx` 응용 프로그램에서 페이지 및 웹 프로젝트의 시작 페이지로 설정 합니다.

다음 표에서 Azure에서 응용 프로그램을 시작 하는 방법에 대 한 세부 정보를 제공 합니다.

   | 웹 응용 프로그램 유형 | Azure에서 실행 |
   | --- | --- | --- |
   | ASP.NET 웹 응용 프로그램<br/>(MVC 2, MVC 3, MVC 4 포함) | URL을 선택 합니다 **배포** 탭의 **Azure 활동 로그**합니다. |
   | ASP.NET 빈 웹 응용 프로그램 | 기본값을 사용 하는 경우 `.aspx` 응용 프로그램에서 페이지의 URL을 선택 합니다는 **배포** 탭의 **Azure 활동 로그**합니다. 다른 페이지로 이동할 브라우저에서 다음 형식의 URL을 입력: `<deployment_url>/<page_name>.aspx` |
   | Silverlight 응용 프로그램<br/>Silverlight 비즈니스 응용 프로그램<br/>Silverlight 탐색 응용 프로그램 | 다음 URL 형식을 사용 하 여 응용 프로그램에 대 한 특정 페이지로 이동 합니다. `<deployment_url>/<page_name>.aspx` |
    WCF Service Application<br/>WCF Workflow 서비스 응용 프로그램 | 설정 된 `.svc` WCF 서비스 프로젝트에 대 한 시작 페이지 파일입니다. 다음으로 이동 `<deployment_url>/<service_file>.svc` |
   | ASP.NET 동적 엔터티<br/>ASP.NET Dynamic Data Linq to SQL | 다음 섹션에 설명 된 대로 연결 문자열을 업데이트 합니다. 다음으로 이동 `<deployment_url>/<page_name>.aspx`합니다. Linq to SQL에서 Azure SQL database를 사용 해야 합니다. |

## <a name="update-a-connection-string-for-aspnet-dynamic-entities"></a>ASP.NET 동적 엔터티의 연결 문자열 업데이트

1. (#Use-an-azuresql-database-for-your-application) 이전에 설명 된 대로 ASP.NET 동적 엔터티 웹 응용 프로그램에 대 한 SQL Azure 데이터베이스를 만듭니다.
1. 테이블 및 Azure portal에서이 데이터베이스에 필요한 필드를 추가 합니다.
1. 연결 문자열을 지정 합니다 `web.config` 다음 형식으로 파일 및 파일을 저장 합니다.

    ```xml
    <addname="tempdbEntities"connectionString="metadata=res://*/Model1.csdl|res://*/Model1.ssdl|res://*/Model1.msl;provider=System.Data.SqlClient;provider connection string=&quot;data source=<server name>\SQLEXPRESS;initial catalog=<database name>;integrated security=True;multipleactiveresultsets=True;App=EntityFramework&quot;"providerName="System.Data.EntityClient"/>
    ```

    업데이트를 *connectionString* SQL Azure 데이터베이스에 대 한 ADO.NET 연결 문자열을 사용 하 여 다음과 같이 값:

    ```xml
    XMLCopy<addname="tempdbEntities"connectionString="metadata=res://*/Model1.csdl|res://*/Model1.ssdl|res://*/Model1.msl;provider=System.Data.SqlClient;provider connection string=&quot;Server=tcp:<SQL Azure server name>.database.windows.net,1433;Database=<database name>;User ID=<user name>;Password=<password>;Trusted_Connection=False;Encrypt=True;multipleactiveresultsets=True;App=EntityFramework&quot;"providerName="System.Data.EntityClient"/>
    ```

## <a name="supported-project-templates"></a>지원 되는 프로젝트 템플릿

응용 프로그램 마이그레이션 및 클라우드 서비스에 게시할 수는 아래 표의 템플릿 중 하나를 사용 해야 합니다. ASP.NET Core 지원 되지 않습니다.

| 템플릿 그룹 | 프로젝트 템플릿 |
| --- | --- |
| 웹 | ASP.NET 웹 응용 프로그램 (.NET Framework) |
| 웹 | ASP.NET MVC 2 웹 응용 프로그램 |
| 웹 | ASP.NET MVC 3 웹 응용 프로그램 |
| 웹 | ASP.NET MVC4 웹 응용 프로그램 |
| 웹 | ASP.NET 빈 웹 응용 프로그램 (또는 사이트) |
| 웹 | ASP.NET MVC 2 빈 웹 응용 프로그램 |
| 웹 | ASP.NET Dynamic Data 엔터티 웹 응용 프로그램 |
| 웹 | ASP.NET Dynamic Data Linq to SQL 웹 응용 프로그램 |
| Silverlight | Silverlight 응용 프로그램 |
| Silverlight | Silverlight 비즈니스 응용 프로그램 |
| Silverlight | Silverlight 탐색 응용 프로그램 |
| WCF | WCF Service Application |
| WCF | WCF Workflow 서비스 응용 프로그램 |
| 워크플로 | WCF Workflow 서비스 응용 프로그램 |

## <a name="next-steps"></a>다음 단계

- [Visual Studio에서 Azure 응용 프로그램 배포 또는 게시 준비](vs-azure-tools-cloud-service-publish-set-up-required-services-in-visual-studio.md)
- [명명 된 인증 자격 증명 설정](vs-azure-tools-setting-up-named-authentication-credentials.md)합니다.
