---
title: Azure에 대 한 명령줄 빌드 | Microsoft Docs
description: Azure에 대 한 명령줄 빌드
author: ghogen
manager: douge
assetId: 94b35d0d-0d35-48b6-b48b-3641377867fd
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/05/2017
ms.author: ghogen
ms.openlocfilehash: fce752d91ebaa765e18efef117a3b6efe750119c
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002938"
---
# <a name="building-azure-projects-from-the-command-line"></a>명령줄에서 Azure 프로젝트 빌드
Microsoft Build Engine (MSBuild)을 사용 하 여 Visual Studio 설치 되지 않은 빌드 랩 환경에서 제품을 빌드할 수 있습니다. MSBuild는 확장 가능 하 고 Microsoft에서 완전히 지원 되는 프로젝트 파일에 대 한 XML 형식으로 사용 합니다. MSBuild 파일 형식을 사용 하 여를 설명할 수 있습니다 해야 할 항목 하나 이상의 플랫폼 및 구성에 대 한 기본 제공 합니다.

명령줄에서 MSBuild를 실행할 수도 있습니다 및이 항목에서는 그 방법을 설명 합니다. 명령줄에서 속성을 설정 하면 프로젝트의 특정 구성을 빌드할 수 있습니다. 마찬가지로, MSBuild가 빌드할 대상을 정의할 수 있습니다. 명령줄 매개 변수 및 MSBuild에 대 한 자세한 내용은 참조 하십시오 [MSBuild 명령줄 참조](https://msdn.microsoft.com/library/ms164311.aspx)합니다.

## <a name="msbuild-parameters"></a>MSBuild 매개 변수
패키지를 만들기 위한 가장 간단한 방법으로 MSBuild를 실행 하는 것은 `/t:Publish` 옵션입니다. 이 명령은 기본적으로 프로젝트의 루트 폴더를 기준으로 디렉터리와 같은 만듭니다 `<ProjectDirectory>\bin\Configuration\app.publish\`합니다. Azure 프로젝트를 빌드할 때 두 파일이 생성 됩니다: 패키지 파일 자체와 함께 제공 되는 구성 파일:

* 패키지 파일 (`project.cspkg`)
* 구성 파일 (`ServiceConfiguration.TargetProfile.cscfg`)

기본적으로 각 Azure 프로젝트에는 로컬 (디버깅) 빌드용 서비스 구성 파일 2 개 및 클라우드 (스테이징 또는 프로덕션) 빌드용 포함 됩니다. 그러나 추가 하거나 필요에 따라 서비스 구성 파일을 제거할 수 있습니다. Visual Studio 내에서 패키지를 빌드하면 패키지와 함께 포함할 서비스 구성 파일 라는 메시지가 표시 됩니다. MSBuild를 사용 하 여 패키지를 빌드하면 로컬 서비스 구성 파일은 기본적으로 포함 됩니다. 다른 서비스 구성 파일을 포함 하려면 설정 합니다 `TargetProfile` MSBuild 속성 (`MSBuild /t:Publish /p:TargetProfile=ProfileName`).

저장 된 패키지 및 구성 파일에 대 한 다른 디렉터리를 사용 하려는 경우 사용 하 여 경로 설정 합니다 `/p:PublishDir=Directory\` 후행 백슬래시 구분 기호를 포함 하 여 옵션입니다.

## <a name="next-steps"></a>다음 단계
패키지를 빌드한 후에 Azure에 배포할 수 있습니다.