---
title: Visual Studio를 사용 하 여 Azure 클라우드 서비스 프로젝트 만들기 | Microsoft Docs
description: Visual Studio를 사용 하 여 Azure 클라우드 서비스 프로젝트를 만드는 방법을 알아봅니다.
author: ghogen
manager: douge
assetId: ec580df7-3dcc-45a9-a1d9-8c110678dfb5
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: 8149f60440becb3c7a8d0dc08b2a1a9c00fb171a
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51003028"
---
# <a name="creating-an-azure-cloud-service-project-with-visual-studio"></a>Visual Studio를 사용 하 여 Azure 클라우드 서비스 프로젝트 만들기
Azure Tools for Visual Studio는 만들 수 있는 프로젝트 템플릿을 제공을 [Azure 클라우드 서비스](/azure/cloud-services/cloud-services-choose-me), 간단한 범용 Azure 서비스인 합니다. 프로젝트를 만든 후 Visual Studio를 사용 하면 구성, 디버그 및 Azure에 클라우드 서비스를 배포할 수 있습니다.

## <a name="steps-to-create-an-azure-cloud-service-project-in-visual-studio"></a>Visual Studio에서 Azure 클라우드 서비스 프로젝트를 만드는 방법
이 섹션에서는 하나 이상의 웹 역할을 사용 하 여 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 만드는 과정 안내 합니다.  

1. 관리자 권한으로 Visual Studio를 시작 합니다.

1. 주 메뉴에서 선택 **파일** > **새로 만들기** > **프로젝트**합니다.

1. 선택 **클라우드** 시각적 개체에서 C# 또는 Visual Basic 프로젝트 템플릿 노드에서 선택한 **Azure Cloud Service** 템플릿 목록에서.

    ![새 Azure 클라우드 서비스](./media/vs-azure-tools-azure-project-create/new-project-wizard-for-cloud-service.png)

1. 프로젝트 개발에 사용 하려는.NET Framework의 버전을 지정 합니다.

1. 이름 및 프로젝트에 대 한 위치 및 솔루션 이름을 입력 합니다. 

1. **확인**을 선택합니다.

1. 에 **새 Microsoft Azure 클라우드 서비스** 대화 상자에 추가 하려는 역할을 선택 하 고 솔루션에 추가 하려면 오른쪽 화살표 단추를 선택 합니다.

    ![새 Azure 클라우드 서비스 역할을 선택 합니다.](./media/vs-azure-tools-azure-project-create/new-cloud-service.png)

1. 추가한 역할의 이름을 바꾸려면 위에 마우스를 가져가면에서 역할을 **새 Microsoft Azure 클라우드 서비스** 대화 상자에서 상황에 맞는 메뉴에서 **이름 바꾸기**합니다. 솔루션 내에서 역할 이름을 변경할 수 있습니다 (에 **솔루션 탐색기**)에 추가 된 후입니다.

    ![Azure 클라우드 서비스 역할의 이름을 바꾸려면](./media/vs-azure-tools-azure-project-create/new-cloud-service-rename.png)

Visual Studio Azure 프로젝트 솔루션에 역할 프로젝트에 대 한 연결 프로젝트도 포함 합니다 *서비스 정의 파일* 하 고 *서비스 구성 파일*:

- **서비스 정의 파일** -프로그램은 필요한 역할을 포함 하 여 응용 프로그램, 끝점 및 가상 머신 크기에 대 한 런타임 설정을 정의 합니다. 
- **서비스 구성 파일** -얼마나 많은 역할의 인스턴스가 실행 되는지와 역할에 대해 정의 된 설정의 값을 구성 합니다. 

이러한 파일에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 Azure 클라우드 서비스에 대 한 역할 구성](vs-azure-tools-configure-roles-for-cloud-service.md)합니다.

## <a name="next-steps"></a>다음 단계
- [Visual Studio를 사용 하 여 Azure 클라우드 서비스 프로젝트에서 역할 관리](./vs-azure-tools-cloud-service-project-managing-roles.md)
