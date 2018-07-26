---
title: Linux의 App Service에 게시
ms.custom: ''
ms.date: 07/23/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: 9f79cef595b3a58426b596fc1019c59b801a02d5
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252364"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Visual Studio를 사용 하 여 Linux의 App Service에 ASP.NET Core 앱 게시

사용할 수는 **게시** Linux의 Azure App Service에 ASP.NET Core 앱을 게시 하는 도구입니다.

사용 하 여 Linux에서 App Service에 배포 합니다 **게시** 도구에는 Visual Studio 2017 버전 15.7에 있어야 합니다.

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-app-service-on-linux"></a>Linux의 App Service에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시** (사용 또는 합니다 **빌드** > **게시** 메뉴 항목).

    ![솔루션 탐색기에서 프로젝트 상황에 맞는 메뉴에서 [게시] 명령을](../deployment/media/quickstart-publish.png "게시 선택")

1. 게시 프로필을 이전에 구성한 경우 합니다 **게시** 사례는 선택에서 창이 나타납니다 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자에서 **App Service Linux**합니다.

    ![Azure App Service를 선택](../deployment/media/quickstart-publish-linux.png "Azure App Service를 선택 합니다.")

1. **게시**를 선택합니다. 합니다 **App Service 만들기** 대화 상자가 나타납니다. 필요한 경우 다음 기본 app service 설정 필드를 입력 하는 경우 Azure 계정으로 로그인 합니다.

    ![App Service 만들기](../deployment/media/quickstart-publish-settings-app-service-linux.png "Azure App Service 만들기")

1. **만들기**를 선택합니다. Visual Studio에 Azure App Service에 앱을 배포 하 고 브라우저에서 웹 앱을 로드 합니다. 프로젝트 속성 **게시** 사이트 URL 및 기타 세부 정보 창에 표시 됩니다.

    ![게시 프로필 요약을 표시 하는 속성 창](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>다음 단계

이 빠른 시작에서는 Linux의 App Service에 배포에 대 한 게시 프로필을 만들려면 Visual Studio를 사용 하는 방법을 알아보았습니다. Azure를 사용 하 여 Linux에 게시에 대 한 자세한 정보를 확인할 수 있습니다.

> [!div class="nextstepaction"]
> [Linux App Service](/azure/app-service/containers/app-service-linux-intro)
