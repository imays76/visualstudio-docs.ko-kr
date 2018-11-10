---
title: 프로젝트를 현재 버전의 Azure 도구로 업그레이드 하는 방법 | Microsoft Docs
description: Visual Studio에서 Azure 프로젝트를 현재 버전의 Azure 도구로 업그레이드 하는 방법 알아보기
author: ghogen
manager: douge
assetId: 1d64070a-078d-468a-87f4-e6715de6475f
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/18/2016
ms.author: ghogen
ms.openlocfilehash: c5fb70f2dd09338dd2e2f6b01cb60bf2be0cdbdd
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002908"
---
# <a name="how-to-upgrade-projects-to-the-current-version-of-the-azure-tools-for-visual-studio"></a>Visual Studio용 Azure 도구의 현재 버전으로 프로젝트를 업그레이드하는 방법
## <a name="overview"></a>개요
Azure Tools를 사용 하 여 생성 된 모든 프로젝트 버전 1.6 전에 Azure 도구 (또는 1.6 이후 버전인는 이전 릴리스의)의 현재 릴리스를 설치한 후 열면 즉시 (2011 년 11 월) 자동으로 업그레이드 됩니다. 이러한 도구의 1.6 (2011 년 11 월) 릴리스를 사용 하 여 프로젝트를 만든 경우 아직 릴리스가 설치 되어 있는 이전 릴리스에서 해당 프로젝트를 열고 하 수 나중에 업그레이드 여부.

## <a name="how-your-project-changes-when-you-upgrade-it"></a>업그레이드 시 프로젝트 변경 하는 방법
프로젝트를 자동으로 업그레이드할 경우 업그레이드 하려는 지정할 특정 어셈블리의 현재 버전을 사용 하 여 프로젝트가 수정 되 고 일부 속성은이 섹션에 설명 된 대로 변경 됩니다. 최신 버전의 도구와 호환 되기 위한 다른 변경을, 프로젝트에 필요한 경우 수동으로 이러한 변경 내용을 확인 해야 합니다.

* 웹 역할에 대 한 web.config 파일 및 작업자 역할에 대 한 app.config 파일은 최신 버전의 Microsoft.WindowsAzure.Diagnostics.DiagnosticMonitoirTraceListener.dll 참조 하도록 업데이트 됩니다.
* Microsoft.WindowsAzure.StorageClient.dll, Microsoft.WindowsAzure.Diagnostics.dll 및 Microsoft.WindowsAzure.ServiceRuntime.dll 어셈블리가 새 버전으로 업그레이드 됩니다.
* Azure 프로젝트 파일 (.ccproj)에 저장 된 게시 프로필을에서 확장명.azurePubXml으로 별도 파일로 이동 합니다 **게시** 하위 디렉터리입니다.
* 게시 프로필의 일부 속성은 새로운 기능과 변경 된 기능을 지원 하도록 업데이트 됩니다. **AllowUpgrade** 바뀝니다 **DeploymentReplacementMethod** 있으므로 증분 또는 동시에 배포 된 클라우드 서비스를 업데이트할 수 있습니다.
* 속성 **UseIISExpressByDefault** 추가 되 고 IIS Express에 디버깅에 사용 되는 웹 서버에서 인터넷 정보 서비스 (IIS)를 자동으로 변경 되지 않습니다 있도록 false로 설정 합니다. IIS Express는 최신 릴리스의 도구를 사용 하 여 만든 프로젝트에 대 한 기본 웹 서버입니다.
* 하나 이상의 프로젝트 역할에서 호스팅되는 Azure Caching을 하는 경우 프로젝트를 업그레이드할 때 서비스 구성 (.cscfg 파일) 및 서비스 정의 (.csdef 파일)의 일부 속성이 변경 됩니다. 프로젝트에서 Azure Caching NuGet 패키지를 사용 하는 경우 프로젝트는 패키지의 최신 버전으로 업그레이드 됩니다. Web.config 파일을 열고 업그레이드 프로세스 중에 클라이언트 구성이 올바르게 유지 되었는지 확인 해야 합니다. NuGet 패키지를 사용 하지 않고 Azure 캐싱 클라이언트 어셈블리에 대 한 참조를 추가한 경우 이러한 어셈블리는 업데이트 되지 않습니다. 새 버전에 대 한 이러한 참조를 수동으로 업데이트 해야 합니다.

> [!IMPORTANT]
> 에 대 한 F# 프로젝트의 경우 이러한 어셈블리의 최신 버전을 참조할 수 있도록 Azure 어셈블리에 대 한 참조를 수동으로 업데이트 해야 합니다.
> 
> 

### <a name="how-to-upgrade-an-azure-project-to-the-current-release"></a>Azure 프로젝트를 현재 릴리스로 업그레이드 하는 방법
1. 업그레이드 된 프로젝트에 사용 하려는 Visual Studio의 설치에 Azure 도구의 현재 버전을 설치 하 고 업그레이드 하려는 프로젝트를 엽니다. Azure Tools를 사용 하 여 프로젝트를 만든 경우 1.6 이전 릴리스 (2011 년 11 월) 프로젝트를 현재 버전으로 자동 업그레이드 됩니다. 프로젝트를 만든 2011 년 11 월 릴리스 및 해당 릴리스가 여전히 설치 된 경우 프로젝트는 해당 릴리스에서 열립니다.
2. 솔루션 탐색기에서 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **속성**를 선택 합니다 **응용 프로그램** 나타나는 대화 상자의 탭 합니다.
   
    합니다 **응용 프로그램** 탭에는 프로젝트와 연결 된 도구 버전을 보여 줍니다. Azure 도구의 현재 버전에 표시 되 면 프로젝트가 이미 업그레이드 되었습니다. 어떤 탭에 표시 하는 보다 최신 버전의 도구를 설치한 경우는 **업그레이드** 단추가 나타납니다.
3. 선택 된 **업그레이드** 도구의 현재 버전으로 프로젝트를 업그레이드 하는 단추입니다.
4. 프로젝트를 빌드하고 API 변경 내용에서 발생 하는 오류를 해결 합니다. 새 버전에 대 한 코드를 수정 하는 방법에 대 한 내용은 특정 API에 대 한 설명서를 참조 하세요.

