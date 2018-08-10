---
title: 로컬 폴더에 배포
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, local folder
ms.assetid: adb461c4-812a-4b8c-b2ab-96002379f6a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 517698aa2e042d74138579dae3633930b338cd61
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38781915"
---
# <a name="deploy-an-app-to-a-local-folder-using-visual-studio"></a>Visual Studio를 사용 하 여 로컬 폴더에 앱 배포

사용할 수는 **게시** 도구를 로컬 폴더로 Visual Studio에서 ASP.NET, ASP.NET Core,.NET Core 및 Python 앱을 게시 합니다. Node.js에 대 한 단계는 지원 되지만 사용자 인터페이스는 다릅니다.

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="deploy-to-a-local-folder"></a>로컬 폴더에 배포

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시** (사용 또는 합니다 **빌드** > **게시** 메뉴 항목).

    ![솔루션 탐색기에서 프로젝트 상황에 맞는 메뉴에서 [게시] 명령을](../deployment/media/quickstart-publish.png "게시 선택")

1. 게시 프로필을 이전에 구성한 경우 합니다 **게시** 창이 나타납니다. 선택 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자에서 **폴더**합니다.

    ![게시 taget 로컬 폴더 선택](../deployment/media/quickstart-publish-folder.png "폴더 선택")

1. 경로 입력 하거나 선택 **찾아보기** 로컬 폴더를 지정할 수 있습니다.

1. **게시**를 선택합니다. Visual Studio 프로젝트를 빌드하고 지정된 된 폴더에 게시 합니다. 프로젝트 속성 **게시** 프로필 요약 표시 창이 나타납니다.

    ![게시 프로필 요약을 표시 하는 속성 창](../deployment/media/quickstart-publish-folder-summary.png)

1. 배포 설정을 구성 하려면 선택 **구성** 요약 선택한 프로필에는 **설정** 탭 합니다.

    ![프로필 설정](../deployment/media/quickstart-profile-settings.png "프로필 설정")

1. 선택한 디버그 또는 릴리스 구성, 배포 여부를 같은 옵션을 구성할 **저장할**합니다.

1. 을 다시 게시 하려면 **게시**합니다.

게시된 파일을 원하는 방식으로 배포합니다. 예를 들어에 패키지할 수 있습니다는 *.zip* 파일, 단순 복사 명령을 사용 하 여 또는 사용자가 선택한 설치 패키지를 사용 하 여 배포 합니다.

## <a name="next-steps"></a>다음 단계

- [게시 도구를 사용하여 .NET Core 응용 프로그램 배포](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Microsoft Store(데스크톱 브리지)의 데스크톱 앱 패키지](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- (.NET) [.NET Framework 및 응용 프로그램 배포](/dotnet/framework/deployment/)
