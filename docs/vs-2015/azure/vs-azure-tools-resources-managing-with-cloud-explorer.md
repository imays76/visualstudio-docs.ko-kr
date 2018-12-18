---
title: 클라우드 탐색기를 사용 하 여 Azure 리소스 관리 | Microsoft Docs
description: 클라우드 탐색기를 사용 하 여 Visual Studio 내에서 Azure 리소스 찾아보기 및 관리 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: 6347dc53-f497-49d5-b29b-e8b9f0e939d7
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/25/2017
ms.author: ghogen
ms.openlocfilehash: a5b75aa5e1310e02befe162199472eef987d7cd9
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002363"
---
# <a name="manage-the-resources-associated-with-your-azure-accounts-in-visual-studio-cloud-explorer"></a>Visual Studio 클라우드 탐색기에서 Azure 계정과 연결된 리소스 관리

클라우드 탐색기를 사용 하면, 리소스 그룹 및 Azure 리소스를 보고 하 고, 해당 속성을 검사 하 고, Visual Studio 내에서 핵심 개발자 진단 작업을 수행할 수 있습니다. 

같은 합니다 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040), Azure Resource Manager 스택에 클라우드 탐색기가 빌드됩니다. 따라서 클라우드 탐색기 Azure 리소스 그룹과 같은 리소스 및 Logic apps 및 API apps와 같은 Azure 서비스를 이해 하 고 지 원하는 [역할 기반 액세스 제어](/azure/role-based-access-control/role-assignments-portal.md) (RBAC). 

## <a name="prerequisites"></a>전제 조건

* Visual Studio 2015를 [Microsoft Azure SDK for.NET 2.9](https://www.microsoft.com/en-us/download/details.aspx?id=51657)합니다.
* Microsoft Azure 계정-계정이 없는, 하는 경우 [무료 평가판에 등록](http://go.microsoft.com/fwlink/?LinkId=623901) 하거나 [Visual Studio 구독자 혜택을 활성화](http://go.microsoft.com/fwlink/?LinkId=623901)합니다.

> [!NOTE]
> 클라우드 탐색기를 보려면 선택 **뷰** > **클라우드 탐색기** 메뉴 모음에서.

## <a name="add-an-azure-account-to-cloud-explorer"></a>추가 Azure 계정을 클라우드 탐색기

Azure 계정과 연결 된 리소스를 보려면 클라우드 탐색기에 계정의 먼저 추가 해야 합니다. 

1. **클라우드 탐색기**를 선택 **Azure 계정 설정**합니다.

   ![클라우드 탐색기 Azure 계정 설정 아이콘](./media/vs-azure-tools-resources-managing-with-cloud-explorer/azure-account-settings.png)

1. 선택 **계정 관리**합니다. 

   ![클라우드 탐색기 계정 추가 링크](./media/vs-azure-tools-resources-managing-with-cloud-explorer/manage-accounts-link.png)

1. 해당 리소스를 검색 하려는 Azure 계정에 로그인 합니다. 

1. Azure 계정에 로그인 한 후 해당 계정과 연결 된 구독이 표시 합니다. 이동한 다음 선택 하려는 계정 구독에 대 한 확인란을 선택 **적용**합니다. 

   ![클라우드 탐색기: 표시할 Azure 구독 선택](./media/vs-azure-tools-resources-managing-with-cloud-explorer/select-subscriptions.png)

1. 해당 리소스를 검색 하려는 구독을 선택한 후 해당 구독 및 리소스가 클라우드 탐색기에 표시 합니다.

   ![클라우드 탐색기 리소스는 Azure 계정에 대 한 목록](./media/vs-azure-tools-resources-managing-with-cloud-explorer/resources-listed.png)

## <a name="remove-an-azure-account-from-cloud-explorer"></a>클라우드 탐색기에서 Azure 계정 제거 

1. **클라우드 탐색기**를 선택 **계정 관리**합니다.

   ![클라우드 탐색기 Azure 계정 설정 아이콘](./media/vs-azure-tools-resources-managing-with-cloud-explorer/azure-account-settings.png)

1. 제거 하려는 계정에 옆에 있는 선택 **계정 관리**합니다.

   ![클라우드 탐색기 Azure 계정 설정 아이콘](./media/vs-azure-tools-resources-managing-with-cloud-explorer/remove-account.png)

1. 선택할 **제거** 계정을 제거 하려면.

    ![클라우드 탐색기 관리 계정 대화 상자](./media/vs-azure-tools-resources-managing-with-cloud-explorer/accountmanage.PNG)

## <a name="view-resource-types-or-resource-groups"></a>리소스 종류 또는 리소스 그룹 보기

Azure 리소스를 보려면 선택할 수 있습니다 **리소스 종류** 하거나 **리소스 그룹** 보기.

1. **클라우드 탐색기**, 리소스 보기 드롭다운을 선택 합니다.

   ![원하는 리소스 보기를 선택 하려면 클라우드 탐색기 드롭다운 목록](./media/vs-azure-tools-resources-managing-with-cloud-explorer/resources-view-dropdown.png)

1. 상황에 맞는 메뉴에서 원하는 보기를 선택 합니다. 

   * **리소스 종류** 뷰-에서 사용 되는 일반적인 보기로 합니다 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040), 웹 앱, 저장소 계정 및 가상 머신과 같은 형식으로 분류 된 Azure 리소스를 보여 줍니다. 
   * **리소스 그룹** 보기-Azure 리소스를 분류 이기 관련 Azure 리소스 그룹입니다. 리소스 그룹은 일반적으로 특정 응용 프로그램에서 사용 하 여 Azure 리소스를 번들입니다. Azure 리소스 그룹에 대 한 자세한 내용은 참조 하세요 [Azure Resource Manager 개요](/azure/azure-resource-manager/resource-group-overview)합니다.

   다음 이미지에서는 두 리소스 보기 비교를 보여 줍니다.

   ![클라우드 탐색기 리소스 보기 비교](./media/vs-azure-tools-resources-managing-with-cloud-explorer/resource-views-comparison.png)

## <a name="view-and-navigate-resources-in-cloud-explorer"></a>클라우드 탐색기에서 리소스 보기 및 탐색

Azure 리소스를 이동한 후 클라우드 탐색기에서 해당 정보를 보려면, 항목의 형식 또는 연결 된 리소스 그룹을 확장 하 고 리소스를 선택 합니다. 리소스를 선택 하면 두 탭에 정보가 나타납니다 **작업** 하 고 **속성** -클라우드 탐색기의 맨 아래에 있습니다.

* **작업** 탭-선택한 리소스에 대 한 클라우드 탐색기에서 수행할 수 있는 작업을 나열 합니다. 또한 리소스 상황에 맞는 메뉴를 마우스 오른쪽 단추로 클릭 하 여 이러한 옵션을 볼 수 있습니다.

* **속성** 탭-와 연결 된 해당 형식, 로캘 및 리소스 그룹과 같은 리소스의 속성을 보여 줍니다.

다음 이미지에 표시 된 각 탭에서 App Service에 대 한 예제 비교를 보여 줍니다.

  ![클라우드 탐색기의 스크린샷](./media/vs-azure-tools-resources-managing-with-cloud-explorer/actions-and-properties.png)

모든 리소스에 action **포털에서 열기**합니다. 이 작업을 선택 하면 클라우드 탐색기에서 선택한 리소스를 표시 합니다 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040)합니다. 합니다 **포털에서 열기** 기능은 깊이 중첩 된 리소스를 탐색 하는 데 편리 합니다.

추가 작업 및 속성 값은 Azure 리소스에 기반을 나타날 수도 있습니다. 예를 들어, web apps 및 logic apps 작업도 있습니다 **브라우저에서 열기** 하 고 **디버거** 외에 **포털에서 열기**합니다. 저장소 계정 blob, 큐 또는 테이블을 선택 하면 편집기를 열려는 작업이 나타납니다. Azure 앱에 **URL** 하 고 **상태** 속성에는 저장소 리소스 키 및 연결 문자열 속성입니다.

## <a name="find-resources-in-cloud-explorer"></a>클라우드 탐색기에서 리소스 찾기

Azure 계정 구독에서 특정 이름의 리소스를 찾으려면에 이름을 입력 합니다 **검색** 클라우드 탐색기에서 상자입니다.

  ![클라우드 탐색기에서 리소스 찾기](./media/vs-azure-tools-resources-managing-with-cloud-explorer/search-for-resources.png)

문자를 입력 합니다 **검색** 상자에서 해당 문자와 일치 하는 리소스만 리소스 트리에 나타납니다.
