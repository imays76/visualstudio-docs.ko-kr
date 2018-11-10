---
title: Visual Studio에서 클라우드 서비스를 게시 또는 배포 준비 | Microsoft Docs
description: 클라우드 및 저장소 계정 서비스를 설정 하 고 Azure 응용 프로그램을 구성 하는 절차에 알아봅니다.
author: ghogen
manager: douge
ms.assetid: 92ee2f9e-ec49-4c7a-900d-620abe5e9d8a
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/10/2017
ms.author: ghogen
ms.openlocfilehash: d7643d87f60b953b9c0928571036c7890e4d11f0
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002978"
---
# <a name="prepare-to-publish-or-deploy-a-cloud-service-from-visual-studio"></a>Visual Studio에서 클라우드 서비스 게시 또는 배포 준비

클라우드 서비스 프로젝트를 게시 하려면이 문서에 설명 된 대로 다음 서비스를 설정 해야 합니다.

* A **클라우드 서비스** Azure 환경에서 역할을 실행 하 고 
* A **저장소 계정** Blob, Queue 및 Table services에 대 한 액세스를 제공 하는 합니다.

## <a name="create-a-cloud-service"></a>클라우드 서비스 만들기

클라우드 서비스는 Azure 환경에서 역할을 실행 합니다. Visual Studio에서 또는 클라우드 서비스를 만들 수 있습니다 합니다 [Azure portal](https://portal.azure.com/) 다음 섹션에 설명 된 대로 합니다.

### <a name="create-a-cloud-service-from-visual-studio"></a>Visual Studio에서 클라우드 서비스 만들기

1. 이전에 만든 클라우드 서비스 프로젝트를 마우스 오른쪽 단추로 클릭는 프로젝트 **게시**합니다.
1. 필요한 경우 Microsoft 또는 조직 계정을 Azure 구독과 연결 된 로그인 한 다음 선택 **다음** 이동 합니다 **설정** 페이지입니다.
1. A **클라우드 서비스 및 저장소 계정 만들기** 대화 상자가 나타납니다 (그렇지 않은 경우 **새로 만들기** 에서 합니다 **클라우드 서비스** 목록).
1. URL의 일부를 형성 하 고 고유 해야 하는 클라우드 서비스에 대 한 대/소문자 구분 이름을 입력 합니다. 또한 지역 또는 선호도 그룹을 선택 하 고 복제 옵션을 선택 합니다.

### <a name="create-a-cloud-service-through-the-azure-portal"></a>Azure portal 통해 클라우드 서비스 만들기

1. [Azure Portal](https://portal.azure.com/)에 로그인합니다.
1. 선택 **Cloud Services (클래식)** 페이지의 왼쪽에 있습니다.
1. 선택 **+ 추가**, 후 (DNS 이름, 구독, 리소스 그룹 및 위치)에 필요한 정보를 제공 합니다. 이렇게 하면 나중에 Visual Studio에서에서 때문에 시점에 패키지를 업로드할 필요는 없습니다.
1. 선택 **만들기** 프로세스를 완료 합니다.

## <a name="create-a-storage-account"></a>저장소 계정 만들기

저장소 계정은 Blob, Queue 및 Table services에 대 한 액세스를 제공 합니다. Visual Studio를 통해 저장소 계정을 만들 수 있습니다 또는 [Azure portal](https://portal.azure.com/)합니다.

### <a name="create-a-storage-account-from-visual-studio"></a>Visual Studio에서 저장소 계정 만들기

1. **솔루션 탐색기** 이전에 만든 클라우드 서비스 프로젝트를 찾습니다는 **연결 된 서비스** 내에서 역할 프로젝트를 마우스 오른쪽 단추로 노드 **연결 된 서비스 추가**. (Visual Studio 2015에서 마우스 오른쪽 단추로 클릭 합니다 **저장소** 노드와 선택 **Storage 계정 만들기**.)
1. 에 **연결 된 서비스** 선택, 표시 된 목록 **Azure Storage를 사용 하 여 클라우드 Storage**합니다.
1. 표시 되는 Azure Storage 대화 상자에서 선택 **+ 새 저장소 계정 만들기**, 구독의 이름을 지정 하는 대화 상자가 fo 계정는 가격 책정 계층, 리소스 그룹 및 위치입니다.
1. 선택 **만들기** 완료 되 면 합니다. 새 저장소 계정을 구독에서 사용 가능한 저장소 계정 목록에 나타납니다.
1. 계정 선택을 선택 **추가**합니다.

### <a name="create-a-storage-account-through-the-azure-portal"></a>Azure portal 통해 저장소 계정 만들기

1. [Azure Portal](https://portal.azure.com/)에 로그인합니다.
1. 선택 **+ 새로 만들기** 왼쪽 위에 있습니다.
1. 선택 **저장소** Marketplace 아래 에서"Azure를" 한 다음 **저장소 계정-blob, 파일, 테이블, 큐** 오른쪽에서입니다.
1. (이름, 배포 모델 및 등 필요한 정보를 제공 합니다.입니다.
1. 선택 **만들기** 프로세스를 완료 합니다.

## <a name="configure-your-app-to-use-the-storage-account"></a>저장소 계정을 사용 하도록 앱 구성

저장소 계정을 만든 후 Url 및 액세스 키를 포함 하 여 프로젝트를 위한 서비스 구성을 업데이트 자동으로 Visual Studio에서 연결 되도록 합니다.

사용 하 여 Visual Studio에서 클라우드 서비스를 만든 경우 합니다 **연결 된 서비스 추가**를 열어 연결을 확인할 수 있습니다 `ServiceConfiguration.Cloud.cscfg` 및 `ServiceConfiguration.Local.cscfg`합니다.

Azure portal 통해 클라우드 서비스를 만든 경우의 동일한 단계에 따라 [Visual Studio에서 저장소 계정을 만들려면](#create-a-storage-account-from-visual-studio) 하지만 기존 계정을 선택 하지 않고 새로 만들기. Visual Studio에는 다음에서 구성을 업데이트합니다.

구성 설정을 수동으로 속성 페이지를 통해 Visual Studio에서 클라우드 서비스 프로젝트에서 해당 역할에 대 한 (역할을 마우스 오른쪽 단추로 클릭 **속성**). 자세한 내용은 [저장소 계정에 연결 문자열 구성](vs-azure-tools-multiple-services-project-configurations.md#configuring-a-connection-string-for-a-storage-account)합니다.

### <a name="about-access-keys"></a>액세스 키 정보

Azure portal에서는 Azure storage 서비스 및 계정의 기본 및 보조 액세스 키의 각 리소스에 액세스 하는 데 사용할 수 있는 Url을 보여 줍니다. 이러한 키를 사용 하 여 저장소 서비스에 대 한 요청을 인증 합니다.

보조 액세스 키를 저장소 계정의 기본 액세스 키를 동일한 액세스를 제공 하 고 기본 액세스 키 손상 될 백업으로 생성 됩니다. 또한 정기적으로 액세스 키를 다시 생성 하는 것이 좋습니다. 보조 키 다시 생성 하는 동안 생성된 된 기본 키를 사용 하도록 수정할 수 있습니다 다음 기본 키를 다시 생성 하는 동안 보조 키를 사용 하는 연결 문자열 설정을 수정할 수 있습니다.

## <a name="next-steps"></a>다음 단계

Visual Studio에서 Azure에 앱 게시에 대 한 자세히 알아보려면, 참조 [Azure Tools를 사용 하 여 클라우드 서비스 게시](vs-azure-tools-publishing-a-cloud-service.md)합니다.
