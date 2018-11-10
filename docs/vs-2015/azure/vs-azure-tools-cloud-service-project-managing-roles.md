---
title: Visual Studio를 사용 하 여 Azure cloud services에서 역할 관리 | Microsoft Docs
description: 추가 Visual Studio를 사용 하 여 Azure cloud services에서 역할을 제거 하는 방법을 알아봅니다.
author: ghogen
manager: douge
assetId: 5ec9ae2e-8579-4e5d-999e-8ae05b629bd1
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: 35221cbf98f26a71e2b4adf0a7178342616ff7c0
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002888"
---
# <a name="managing-roles-in-azure-cloud-services-with-visual-studio"></a>Visual Studio를 사용 하 여 Azure cloud services에서 역할 관리
Azure 클라우드 서비스를 만든 후에 새 역할을 추가 하거나 기존 역할에서 제거할 수 있습니다. 또한 기존 프로젝트 가져오기 하 고 역할을 변환할 수 있습니다. 예를 들어, ASP.NET 웹 응용 프로그램를 가져오고 웹 역할로 지정할 수 있습니다.

## <a name="adding-a-role-to-an-azure-cloud-service"></a>Azure 클라우드 서비스에 역할 추가
다음 단계를 안내 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 웹 또는 작업자 역할을 추가 합니다.

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**, 프로젝트 노드를 확장 합니다.

1. 마우스 오른쪽 단추로 클릭 합니다 **역할** 노드 상황에 맞는 메뉴를 표시 합니다. 상황에 맞는 메뉴에서 선택 **추가**, 한 다음 현재 솔루션에서 기존 웹 역할 또는 작업자 역할을 선택 하거나 웹 또는 작업자 역할 프로젝트를 만듭니다. 또한 ASP.NET 웹 응용 프로그램 프로젝트와 같은 적절 한 프로젝트를 선택 하 고 역할 프로젝트에 연결할 수 있습니다.

    ![Azure 클라우드 서비스 프로젝트 역할을 추가 하는 메뉴 옵션](./media/vs-azure-tools-cloud-service-project-managing-roles/add-role.png)

## <a name="removing-a-role-from-an-azure-cloud-service"></a>Azure 클라우드 서비스에서 역할 제거
다음 단계를 안내 Visual Studio에서 Azure 클라우드 서비스 프로젝트에서 웹 또는 작업자 역할을 제거 합니다.

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**, 프로젝트 노드를 확장 합니다.

1. 확장 된 **역할** 노드.

1. 를 제거 하 고 상황에 맞는 메뉴에서 선택 하려는 노드를 마우스 오른쪽 단추로 클릭 **제거**합니다. 

    ![Azure 클라우드 서비스 역할을 추가 하는 메뉴 옵션](./media/vs-azure-tools-cloud-service-project-managing-roles/remove-role.png)

## <a name="readding-a-role-to-an-azure-cloud-service-project"></a>Azure 클라우드 서비스 프로젝트에 역할을 다시 추가
클라우드 서비스 프로젝트에서 역할을 제거 해도 나중에 다시 프로젝트에 역할을 추가 하려는 경우 역할 선언과 기본 특성인, 끝점 및 진단 정보 등 추가 됩니다. 참조 또는 레퍼런스 추가할 합니다 `ServiceDefinition.csdef` 파일 또는 `ServiceConfiguration.cscfg` 파일입니다. 이 정보를 추가 하려는 경우 이러한 파일에 다시 수동으로 추가 해야 합니다.

예를 들어, 웹 서비스 역할을 제거할 수 있습니다 하 고 나중에 솔루션에 다시이 역할을 추가 하려면. 이 작업을 수행 하는 경우 오류가 발생 했습니다. 이 오류를 방지 하려면 추가 해야 합니다 `<LocalResources>` 다시 다음 XML에 표시 된 요소는 `ServiceDefinition.csdef` 파일입니다. 에 대 한 이름 특성의 일부로 프로젝트에 다시 추가한 웹 서비스 역할의 이름을 사용 합니다 **<LocalStorage>** 요소입니다. 이 예제에서는 웹 서비스 역할의 이름은 **WCFServiceWebRole1**합니다.

    <WebRole name="WCFServiceWebRole1">
        <Sites>
          <Site name="Web">
            <Bindings>
              <Binding name="Endpoint1" endpointName="Endpoint1" />
            </Bindings>
          </Site>
        </Sites>
        <Endpoints>
          <InputEndpoint name="Endpoint1" protocol="http" port="80" />
        </Endpoints>
        <Imports>
          <Import moduleName="Diagnostics" />
        </Imports>
       <LocalResources>
          <LocalStorage name="WCFServiceWebRole1.svclog" sizeInMB="1000" cleanOnRoleRecycle="false" />
       </LocalResources>
    </WebRole>

## <a name="next-steps"></a>다음 단계
- [Visual Studio에서 Azure 클라우드 서비스에 대 한 역할 구성](vs-azure-tools-configure-roles-for-cloud-service.md)
