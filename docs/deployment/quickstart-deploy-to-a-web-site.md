---
title: 웹 사이트에 게시
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
- multiple
ms.openlocfilehash: 036d7549995f79808142c3a0a64e7e5f2075df2c
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077505"
---
# <a name="publish-a-web-app-to-a-web-site-using-visual-studio"></a>Visual Studio를 사용 하 여 웹 사이트에 웹 앱 게시

사용할 수는 **게시** 도구를 Visual Studio에서 웹 사이트에 ASP.NET, ASP.NET Core,.NET Core 및 Python 앱을 게시 합니다. Node.js에 대 한 단계는 지원 되지만 사용자 인터페이스는 다릅니다.

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="publish-to-a-web-site"></a>웹 사이트에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **게시** (사용 또는 합니다 **빌드** > **게시** 메뉴 항목).

    ![솔루션 탐색기에서 프로젝트 상황에 맞는 메뉴에서 [게시] 명령을](../deployment/media/quickstart-publish.png "게시 선택")

1. 게시 프로필을 이전에 구성한 경우 합니다 **게시** 창이 나타납니다. 선택 **새 프로필 만들기**합니다.

1. 에 **게시 대상 선택** 대화 상자에서 **IIS, FTP 등**합니다.

    ![IIS, FTP 등 선택](../deployment/media/quickstart-publish-iis-ftp.png "선택 IIS, FTP 등입니다.")

1. **게시**를 선택합니다. 프로필 게시 설정 대화 상자가 열립니다.

    ![폴더 선택](../deployment/media/quickstart-publish-settings-web.png "폴더를 선택 합니다.")

1. 에 **게시 방법** 필드를 같은 메서드를 선택 **Web Deploy** 또는 **FTP**. 다음 표시 되는 설정을 게시 방법에 해당 합니다. 웹 배포는 IIS 서버에 웹 응용 프로그램 및 웹 사이트의 배포를 간소화 하 고 서버에서 응용 프로그램으로 설치 해야 합니다. 사용 된 [웹 플랫폼 설치 관리자](https://www.microsoft.com/web/downloads/platform.aspx) 설치 합니다.

1. 게시 방법에 대 한 필수 설정을 구성 하 고 선택 **연결 유효성 검사**합니다. 서버 또는 대상 사용할 수 있고 설정이 연결을 나타내는 메시지의 유효성을 검사 하 고 게시할 준비가 되었습니다. 잘못 된 합니다.

    ![연결의 유효성을 검사](../deployment/media/quickstart-publish-web-deploy.png "연결 확인")

1. 선택 **설정을** 디버그 또는 릴리스 구성, 배포 및 선택 여부와 같은 다른 배포 설정을 구성 하려면 **저장**합니다. 원격으로 디버그 하는 경우는 디버그 구성은 필요 합니다.

1. 게시 하려면 선택 합니다 **게시**합니다. 출력 창에는 배포 진행률 및 결과 보여 줍니다.

## <a name="next-steps"></a>다음 단계

이 빠른 시작에서는 게시 프로필을 만들려면 Visual Studio를 사용 하는 방법을 알아보았습니다. 게시를 구성할 수도 있습니다 게시 설정을 가져와서 프로필입니다.

> [!div class="nextstepaction"]
> [게시 설정 가져오기 및 IIS에 배포](tutorial-import-publish-settings-iis.md)
