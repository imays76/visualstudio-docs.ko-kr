---
title: Visual Studio를 사용 하 여 Azure 응용 프로그램 게시 마법사 | Microsoft Docs
description: Visual Studio 게시 Azure 응용 프로그램 마법사에서 다양 한 설정을 구성 하는 방법 알아보기
author: ghogen
manager: douge
assetId: 7d8f1ac9-e439-47e0-a183-0642c4ea1920
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: c9c4104d4d07cab7486038a8787ed0c7759abd60
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002968"
---
# <a name="using-the-visual-studio-publish-azure-application-wizard"></a>Visual Studio [Azure 응용 프로그램 게시] 마법사 사용

Visual Studio에서 웹 응용 프로그램을 개발한 후 사용 하 여 Azure 클라우드 서비스에 해당 응용 프로그램을 게시할 수 있습니다 합니다 **Azure 응용 프로그램 게시** 마법사.

> [!Note]
> 이 문서에서는 웹 사이트가 아닌 클라우드 서비스를 배포 하는 방법에 대 한 경우 웹 사이트에 배포 하는 방법에 대 한 내용은 [Azure 웹 사이트를 배포 하는 방법을](https://social.msdn.microsoft.com/Search/windowsazure?query=How%20to%20Deploy%20an%20Azure%20Web%20Site&Refinement=138&ac=4#refinementChanges=117&pageNumber=1&showMore=false)합니다.

## <a name="accessing-the-publish-azure-application-wizard"></a>Azure 응용 프로그램 게시 마법사에 액세스

Visual Studio 프로젝트의 유형에 따라 두 가지 방법으로 Azure 응용 프로그램 게시 마법사를 액세스할 수 있습니다.

**Azure 클라우드 서비스 프로젝트를 있는 경우:**

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭, 상황에 맞는 메뉴에서 선택 **게시**합니다.

**Azure에 대 한 사용 되지 않는 웹 응용 프로그램 프로젝트를 있는 경우:**

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭, 상황에 맞는 메뉴에서 선택 **변환** > **Azure 클라우드 서비스 프로젝트로 변환**합니다. 

1. **솔루션 탐색기**, 새로 만든된 Azure 프로젝트를 마우스 오른쪽 단추로 클릭 하 고, 상황에 맞는 메뉴에서 선택 **게시**합니다.

## <a name="sign-in-page"></a>로그인 페이지

![로그인 페이지](./media/vs-azure-tools-publish-azure-application-wizard/sign-in.png)

**계정** 계정을 선택 하거나 선택- **계정 추가** 계정 드롭다운 목록에서.

**구독 선택** -배포에 사용할 구독을 선택 합니다.

## <a name="settings-page---common-settings-tab"></a>설정 페이지-일반 설정 탭

![일반 설정](./media/vs-azure-tools-publish-azure-application-wizard/settings-common-settings.png)

**클라우드 서비스** -기존 클라우드 서비스 용인지 선택 하거나 선택 드롭다운을 사용 하 여  **&lt;새로 만들기 >**, 클라우드 서비스를 만듭니다. 데이터 센터가 각 클라우드 서비스에 대 한 괄호 안에 표시 됩니다. 데이터 센터 위치 하는 클라우드 서비스에 대 한 저장소 계정 (고급 설정)에 대 한 데이터 센터 위치와 동일 하 게 하는 것이 좋습니다.

**환경** -선택 **프로덕션** 하거나 **스테이징**합니다. 테스트 환경에서 응용 프로그램을 배포 하려는 경우 스테이징 환경을 선택 합니다. 

**빌드 구성** -선택 **디버그** 하거나 **릴리스**합니다.

**서비스 구성** -선택 **클라우드** 하거나 **로컬**합니다.

**모든 역할에 대 한 원격 데스크톱 사용** -서비스에 원격으로 연결할 수 있게 되기를 원하는 경우이 옵션을 선택 합니다. 이 옵션은 주로 문제 해결을 위해 사용 됩니다. 자세한 내용은 [Visual Studio를 사용 하 여 Azure Cloud Services에서 역할에 대 한 원격 데스크톱 연결 사용](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)합니다.

**모든 웹 역할에 대해 웹 배포 사용** -서비스에 대 한 웹 배포를 사용 하도록 설정 하려면이 옵션을 선택 합니다. 선택 해야 합니다 **모든 역할에 대 한 원격 데스크톱 사용** 이 기능을 사용 하는 옵션입니다. 자세한 내용은 [Visual Studio를 사용 하 여 클라우드 서비스 게시](vs-azure-tools-publishing-a-cloud-service.md)합니다.

## <a name="settings-page---advanced-settings-tab"></a>설정 페이지-고급 설정 탭

![고급 설정](./media/vs-azure-tools-publish-azure-application-wizard/settings-advanced-settings.png)

**배포 레이블** -기본 이름을 그대로 적용 하거나 원하는 이름을 입력 합니다. 배포 레이블에 날짜를 추가할 확인란을 선택한 상태로 둡니다. 

**저장소 계정** -이 배포에 사용할 저장소 계정을 선택 * *&lt;새로 만들기 > storage 계정을 만들 수 있습니다. 데이터 센터가 각 저장소 계정에 대 한 괄호 안에 표시 됩니다. 저장소 계정에 대 한 데이터 센터 위치 (일반 설정) 클라우드 서비스에 대 한 데이터 센터 위치와 동일 하지 않는 것이 좋습니다.

응용 프로그램 배포에 대 한 패키지를 저장 하는 Azure storage 계정. 응용 프로그램을 배포한 후 패키지는 저장소 계정에서 제거 됩니다.

**실패 시 배포 삭제** -배포를 게시 하는 동안 오류가 발생 하는 경우를 삭제 하려면이 옵션을 선택 합니다. 이 선택을 취소 해야 클라우드 서비스의 상수 가상 IP 주소를 유지 하려는 경우.

**배포 업데이트** -업데이트 된 구성 요소만 배포 하려는 경우이 옵션을 선택 합니다. 이 유형의 배포는 전체 배포 보다 빠를 수 있습니다. 클라우드 서비스의 상수 가상 IP 주소를 유지 하려는 경우이 확인 해야 합니다. 

**배포 업데이트-설정** -원하는 역할을 업데이트 하는 방법을 자세히 지정 하려면이 대화 상자를 사용 합니다. 선택 하면 **증분 업데이트**, 응용 프로그램의 각 인스턴스를 업데이트할 경우 다른 응용 프로그램은 항상 사용할 수 있도록 합니다. 선택 하면 **동시 업데이트**, 응용 프로그램의 모든 인스턴스가 동시에 업데이트 됩니다. 빠릅니다 동시 업데이트 되지만 업데이트 과정에서 인해 서비스를 사용할 수 있습니다.

![배포 설정](./media/vs-azure-tools-publish-azure-application-wizard/deployment-settings.png)

**IntelliTrace를 사용 하도록 설정** -IntelliTrace를 사용 하도록 설정 하려는 경우를 지정 합니다. IntelliTrace를 사용 하 여 Azure에서 실행 될 때 역할 인스턴스에 대 한 포괄적인 디버깅 정보를 기록할 수 있습니다. 문제의 원인을 확인 하는 경우에 Azure에서 실행 되는 것 처럼 Visual Studio에서 코드를 단계별로 IntelliTrace 로그를 사용할 수 있습니다. IntelliTrace를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Visual Studio 및 IntelliTrace를 사용 하 여 게시 된 Azure 클라우드 서비스 디버깅](./vs-azure-tools-intellitrace-debug-published-cloud-services.md)합니다.

**프로 파일링** -성능 프로 파일링을 사용 하도록 설정 하려는 경우를 지정 합니다. Visual Studio 프로파일러를 사용 하면 클라우드 서비스 실행 방식의 계산 측면을 자세히 분석할 수 있습니다. Visual Studio 프로파일러를 사용 하 여 자세한 내용은 [Azure 클라우드 서비스의 성능을 테스트](./vs-azure-tools-performance-profiling-cloud-services.md)합니다.

**모든 역할에 대해 원격 디버거 사용** -원격 디버깅을 사용 하려는 경우를 지정 합니다. Visual Studio를 사용 하 여 클라우드 서비스 디버깅에 대 한 자세한 내용은 참조 하세요. [Azure 클라우드 서비스 또는 가상 컴퓨터에서 Visual Studio 디버깅](./vs-azure-tools-debug-cloud-services-virtual-machines.md)합니다.

## <a name="diagnostics-settings-page"></a>진단 설정 페이지

![진단 설정](./media/vs-azure-tools-publish-azure-application-wizard/diagnostic-settings.png)

진단을 사용 하는 Azure 클라우드 서비스 (또는 Azure 가상 머신)을 해결할 수 있습니다. 진단에 대 한 자세한 내용은 [Azure Cloud Services 및 Virtual Machines 용 진단 구성](./vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines.md)합니다. Application Insights에 대 한 정보를 참조 하세요 [Application Insights 란?](/azure/application-insights/app-insights-overview.md)합니다.

## <a name="summary-page"></a>요약 페이지

![요약](./media/vs-azure-tools-publish-azure-application-wizard/summary.png)

**대상 프로필** -선택한 설정에서 게시 프로필을 만들 수 있습니다. 예를 들어 하나 테스트 환경용 프로필과 프로덕션 환경용를 만들 수 있습니다. 이 프로필을 저장 하려면 선택 합니다 **저장할** 아이콘입니다. 프로필이 만들어지고 Visual Studio 프로젝트에 저장 됩니다. 프로필 이름을 수정 하려면 엽니다는 **대상 프로필** 목록에서 선택한 다음  **&lt;관리... &gt;**.

   > [!Note]
   > Visual Studio의 솔루션 탐색기에서 게시 프로필이 나타나고 프로 파일 설정이.azurePubxml 확장자로 파일에 기록 됩니다. 설정은은 XML 태그의 특성으로 저장 됩니다.

## <a name="publishing-your-application"></a>응용 프로그램 게시

프로젝트의 배포에 대 한 모든 설정을 구성한 후 선택 **게시** 대화 상자의 맨 아래에 있습니다. 프로세스 상태를 모니터링할 수 있습니다 합니다 **출력** Visual Studio의 창.

## <a name="next-steps"></a>다음 단계

- [마이그레이션 및 Visual Studio에서 Azure 클라우드 서비스에 웹 응용 프로그램 게시](./vs-azure-tools-migrate-publish-web-app-to-cloud-service.md)

- [Azure 클라우드 서비스를 게시 하려면 Visual Studio를 사용 하는 방법 알아보기](./vs-azure-tools-publishing-a-cloud-service.md)

- [Visual Studio 및 IntelliTrace를 사용 하 여 게시 된 Azure 클라우드 서비스 디버깅](./vs-azure-tools-intellitrace-debug-published-cloud-services.md)

- [Azure 클라우드 서비스의 성능을 테스트 합니다.](./vs-azure-tools-performance-profiling-cloud-services.md)

- [Azure Cloud Services 및 Virtual Machines에서 진단 구성](./vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines.md)합니다.

- [Application Insights 란?](/azure/application-insights/app-insights-overview.md)