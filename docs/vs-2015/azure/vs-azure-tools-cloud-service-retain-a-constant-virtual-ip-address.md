---
title: Azure 클라우드 서비스의 상수 가상 IP 주소를 유지 하는 방법 | Microsoft Docs
description: Azure 클라우드 서비스의 가상 IP 주소 (VIP)가 변경 되지 않도록 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: 4a58e2c6-7a79-4051-8a2c-99182ff8b881
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: e74cc5b9bbbfea92d2dea2c00ee5b0f98dc02f21
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002898"
---
# <a name="retain-a-constant-virtual-ip-address-for-an-azure-cloud-service"></a>Azure 클라우드 서비스의 가상 IP 주소를 일정하게 유지
Azure에서 호스트 되는 클라우드 서비스를 업데이트 하면 서비스의 가상 IP 주소 (VIP) 변경 되지 않는지 확인 해야 합니다. 많은 도메인 관리 서비스는 도메인 이름 등록에 대 한 도메인 이름 시스템 (DNS)를 사용 합니다. DNS는 VIP 동일 하 게 유지 하는 경우에 작동 합니다. 사용할 수는 **게시 마법사** 업데이트에서 Azure 클라우드 서비스의 VIP는 경우 변경 되지 않는지 확인 하는 도구입니다. 클라우드 서비스에 대 한 DNS 도메인 관리를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Azure 클라우드 서비스에 대 한 사용자 지정 도메인 이름 구성](/azure/cloud-services/cloud-services-custom-domain-name-portal)합니다.

## <a name="publish-a-cloud-service-without-changing-its-vip"></a>VIP를 변경 하지 않고 클라우드 서비스 게시
클라우드 서비스의 VIP는 처음 배포할 때 Azure에는 프로덕션 환경과 같은 특정 환경에서 할당 됩니다. VIP는 배포를 명시적으로 삭제 하거나 배포 배포 업데이트 프로세스에 의해 암시적으로 삭제 하는 경우에 변경 합니다. VIP를 유지 하려면 배포를 삭제 해서는 및 Visual Studio 배포를 자동으로 삭제 하지 않도록 해야 합니다. 

배포 설정을 지정할 수 있습니다 합니다 **게시 마법사**, 여러 배포 옵션을 지 원하는 합니다. 새로 배포 또는 증분 또는 동시 업데이트 배포를 지정할 수 있습니다. 두 종류의 업데이트 배포 모두 VIP를 유지 합니다. 이러한 다양 한 배포의 정의 참조 하세요 [Azure 응용 프로그램 게시 마법사](vs-azure-tools-publish-azure-application-wizard.md)합니다. 또한 클라우드 서비스의 이전 배포 오류가 발생 하면 삭제 되었는지 여부를 제어할 수 있습니다. 이 옵션을 올바르게 설정 하지 VIP가 예기치 않게 변경 될 수 있습니다.

## <a name="update-a-cloud-service-without-changing-its-vip"></a>VIP를 변경 하지 않고 클라우드 서비스를 업데이트 합니다.
1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다. 

2. **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 합니다. 바로 가기 메뉴에서 선택 **게시**합니다.

    ![게시 메뉴](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/solution-explorer-publish-menu.png)

3. 에 **Azure 응용 프로그램 게시** 대화 상자에서 배포 하려는 Azure 구독을 선택 합니다. 필요에 따라 선택한 경우 로그인 **다음**합니다.

    ![Azure 응용 프로그램 로그인 페이지를 게시 합니다.](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-signin.png)

4. 에 **일반 설정** 탭에서 확인 배포 중인 클라우드의 이름 서비스의 **환경**의 **빌드 구성을**, 및 합니다 **서비스 구성** 이 모두 올바른지 확인 합니다.

    ![Azure 응용 프로그램에 대 한 일반 설정 탭 게시](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-common-settings.png)

5. 에 **고급 설정** 탭에서 확인 합니다 **배포 레이블** 및 **저장소 계정** 올바른지 합니다. 있는지 확인 합니다 **실패 시 배포 삭제** 확인란의 선택을 취소 하 고 있는지 확인 합니다 **배포 업데이트** 확인란을 선택 합니다. 선택을 취소 하 여 합니다 **실패 시 배포 삭제** 배포 하는 동안 오류가 발생 하면 VIP는 손실 되지 않도록 확인란을 있습니다. 선택 하 여 합니다 **배포 업데이트** 배포가 삭제 되지 않습니다 하 고 응용 프로그램을 게시할 때 VIP가 손실 되지 않도록 확인란 합니다. 

    ![Azure 게시 응용 프로그램 고급 설정 탭](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-advanced-settings.png)

6. 추가 하려는 업데이트할 수 있는 역할을 지정 하려면 **설정을** 옆에 **배포 업데이트**합니다. 중 하나를 선택 **증분 업데이트** 하거나 **동시 업데이트**를 선택 하 고 **확인**합니다. 선택할 **증분 업데이트** 응용 프로그램은 항상 사용할 수 있도록 응용 프로그램의 각 인스턴스가 차례로 업데이트 합니다. 선택할 **동시 업데이트** 동시 응용 프로그램의 모든 인스턴스를 업데이트 합니다. 빠릅니다 동시 업데이트 되지만 업데이트 과정에서 인해 서비스를 사용할 수 있습니다. 작업을 완료 하는 경우 선택할 **다음**합니다.

    ![Azure 응용 프로그램 배포 설정 페이지를 게시 합니다.](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-deployment-update-settings.png)

7. 에 **Azure 응용 프로그램 게시** 대화 상자에서 **다음** 때까지 합니다 **요약** 페이지가 표시 됩니다. 설정을 확인 하 고 선택한 **게시**합니다.
   
    ![Azure 응용 프로그램 요약 페이지 게시](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-summary.png)

## <a name="next-steps"></a>다음 단계
- [Visual Studio를 사용 하 여 Azure 응용 프로그램 게시 마법사](vs-azure-tools-publish-azure-application-wizard.md)

