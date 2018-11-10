---
title: Visual Studio를 사용 하 여 Azure 클라우드 서비스 프로젝트 구성 | Microsoft Docs
description: 해당 프로젝트에 대 한 요구 사항에 따라 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 구성 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: 609d6965-05cc-47b1-82dc-c76a92d4f295
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/06/2017
ms.author: ghogen
ms.openlocfilehash: 7417bc117de7dc472f413dd9145944cad2d48bb4
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002953"
---
# <a name="configure-an-azure-cloud-service-project-with-visual-studio"></a>Visual Studio를 사용하여 Azure 클라우드 서비스 프로젝트 구성
해당 프로젝트에 대 한 요구 사항에 따라 Azure 클라우드 서비스 프로젝트를 구성할 수 있습니다. 다음 범주에 대 한 프로젝트에 대 한 속성을 설정할 수 있습니다.

- **Azure에 클라우드 서비스 게시** -Azure에 배포 된 기존 클라우드 서비스가 실수로 삭제 되지 않도록 속성을 설정할 수 있습니다.
- **로컬 컴퓨터의 클라우드 서비스를 실행 또는 디버그할** -서비스 구성을 사용 하 여 Azure 저장소 에뮬레이터를 시작할 것인지를 선택할 수 있습니다.
- **만들어질 때 클라우드 서비스 패키지의 유효성을 검사** -클라우드 서비스 패키지가 문제 없이 배포를 확인할 수 있도록 모든 경고를 오류로 처리 하도록 결정할 수 있습니다. 

## <a name="steps-to-configure-an-azure-cloud-service-project"></a>Azure 클라우드 서비스 프로젝트를 구성 하는 단계
1. Visual Studio에서 클라우드 서비스 프로젝트를 만들거나 열

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭, 상황에 맞는 메뉴에서 선택 **속성**합니다.
   
1. 프로젝트의 속성 페이지에서 선택 합니다 **개발** 탭 합니다.

    ![프로젝트 속성 메뉴](./media/vs-azure-tools-configuring-an-azure-project/solution-explorer-project-properties-menu.png)

1. 설정할 **기존 배포를 삭제 하기 전** 하 **True**합니다. Azure의 기존 배포가 실수로 삭제 되지 않도록 하려면이 설정을 사용 하면

1. 원하는 **서비스 구성** 서비스 구성을 지정 하려면를 실행 하거나 클라우드 서비스를 로컬로 디버깅할 때 사용 합니다. 역할에 대 한 서비스 구성을 수정 하는 방법에 대 한 자세한 내용은 참조 하세요. [Visual Studio를 사용 하 여 Azure 클라우드 서비스에 대 한 역할을 구성 하는 방법을](./vs-azure-tools-configure-roles-for-cloud-service.md)합니다.

1. 설정 **Azure 저장소 에뮬레이터 시작** 하 **True** 실행 또는 클라우드 서비스를 로컬로 디버깅할 때 Azure 저장소 에뮬레이터를 시작 합니다.

1. 설정 **경고를 오류로 처리** 하 **True** 패키지 유효성 검사 오류가 있을 경우 게시 하지 되도록 합니다.

1. 설정할 **웹 프로젝트 포트 사용** 하 **True** 웹 역할이 동일한 포트를 사용 하는지 확인 하려면 시작 될 때마다 IIS Express에서 로컬로 합니다.

1. Visual Studio 도구 모음에서 선택 **저장할**합니다.

## <a name="next-steps"></a>다음 단계
- [여러 서비스 구성을 사용 하 여 Azure 프로젝트 구성](vs-azure-tools-multiple-services-project-configurations.md)

