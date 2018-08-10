---
title: Azure App Service에 게시
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: a8de7175b33a91c310da4b3d6d9e4c05c40c3522
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341692"
---
# <a name="publish-a-web-app-to-azure-app-service-using-visual-studio"></a>Visual Studio를 사용 하 여 Azure App Service에 웹 앱 게시

사용할 수는 **게시** Azure App Service 또는 Azure App Service Linux (컨테이너를 사용 하 여)에 ASP.NET, ASP.NET Core, Node.js 및.NET Core 앱을 게시 하는 도구입니다. Python 앱에 대 한 단계에 따라 [Python-Azure App Service에 게시](../python/publishing-python-web-applications-to-azure-from-visual-studio.md)합니다.

[!INCLUDE [quickstart-prereqs-azure](includes/quickstart-prereqs-azure.md)]

## <a name="publish-to-azure-app-service"></a>Azure App Service에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시** (사용 또는 합니다 **빌드** > **게시** 메뉴 항목).

    ![솔루션 탐색기에서 프로젝트 상황에 맞는 메뉴에서 [게시] 명령을](../deployment/media/quickstart-publish.png "게시 선택")

1. 게시 프로필을 이전에 구성한 경우 합니다 **게시** 사례는 선택에서 창이 나타납니다 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자에서 **App Service**합니다.

    ![Azure App Service를 선택](../deployment/media/quickstart-publish-azure.png "Azure App Service를 선택 합니다.")

1. **게시**를 선택합니다. 합니다 **App Service 만들기** 대화 상자가 나타납니다. 필요한 경우 다음 기본 app service 설정 필드를 입력 하는 경우 Azure 계정으로 로그인 합니다.

    ![App Service 만들기](../deployment/media/quickstart-publish-settings-app-service.png "Azure App Service 만들기")

1. **만들기**를 선택합니다. Visual Studio에 Azure App Service에 앱을 배포 하 고 브라우저에서 웹 앱을 로드 합니다. 프로젝트 속성 **게시** 사이트 URL 및 기타 세부 정보 창에 표시 됩니다.

    ![게시 프로필 요약을 표시 하는 속성 창](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="clean-up-resources"></a>리소스 정리

이전 단계에서는 리소스 그룹에서 Azure 리소스를 만들었습니다. 나중에 이러한 리소스가 필요 하지 않을, 경우에 리소스 그룹을 삭제 하 여 삭제할 수 있습니다.
Azure portal의 왼쪽된 메뉴에서 선택 **리소스 그룹** 선택한 후 **myResourceGroup**합니다.
리소스 그룹 페이지에서 나열 된 리소스를 삭제 하려는 항목 인지를 확인 합니다.
선택 **삭제할**, 형식 **myResourceGroup** 에서 텍스트 상자를 선택 합니다 **삭제**합니다.

## <a name="next-steps"></a>다음 단계

이 빠른 시작에서는 Azure에 배포에 대 한 게시 프로필을 만들려면 Visual Studio를 사용 하는 방법을 알아보았습니다. 게시를 구성할 수도 있습니다를 가져와서 프로필 게시 Azure App Service에서 설정 합니다.

> [!div class="nextstepaction"]
> [게시 설정 가져오기 및 Azure에 배포](tutorial-import-publish-settings-azure.md)
