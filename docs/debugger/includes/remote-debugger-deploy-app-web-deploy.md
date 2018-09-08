---
title: 웹 배포를 사용 하 여 배포
description: Visual Studio에서 웹 배포를 사용 하 여 앱 배포
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 8c843ffa6abcb7517ebfe7cdfb0e742a5f244e07
ms.sourcegitcommit: aea5cdb76fbc7eb31d1e5cc3c8d6adb0c743220f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "34478315"
---
웹 플랫폼 설치 관리자를 사용 하 여 웹 배포를 설치한 경우 Visual Studio에서 직접 앱을 배포할 수 있습니다.

1. 관리자 권한으로 Visual Studio를 시작 하 고 프로젝트를 다시 엽니다.

    웹 배포를 사용 하 여 앱을 배포 하려면 관리자 권한이 필요 합니다.

1. **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

    게시 프로필을 이전에 구성한 경우 합니다 **게시** 창이 나타납니다. 클릭 **새 프로필**합니다.

1. 에 대 한 **게시 대상 선택**를 선택 **IIS, FTP 등** 클릭 **게시**합니다.

    ![RemoteDBG_Publish_IISl](../media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

1. IIS 설정에 대 한 수정 구성 매개 변수를 입력 합니다.

    ![RemoteDBG_Publish_WebDeployl](../media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    유효성을 검사 하려는 경우 호스트 이름을 해결 되지 않으면 다음 단계에서는 합니다 **Server** 텍스트 상자에 IP 주소를 시도 합니다. 포함 `http://` 접두사로 합니다 **Server** 필드입니다.  포트 80을 사용 해야 합니다 **서버** 텍스트 상자의 및 포트 80이 방화벽에서 열려 있는지 확인 합니다.

1. 클릭 **다음**, 선택는 **디버그** 구성 선택 **대상에서 추가 파일 제거** 아래를 **파일 게시** 옵션.

    > [!NOTE]
    > 릴리스 구성을 선택 하면, 게시할 때 web.config 파일에서 디버깅 비활성화할 수 있습니다.

1. 클릭 **Prev**를 선택한 후 **유효성 검사**합니다. 연결 설정의 유효성을 검사 하는 경우에 게시를 시도할 수 있습니다.

1. 클릭 **게시** 앱을 게시 합니다.

    출력 탭이 보여줍니다 경우 게시에 성공 하면 브라우저가 그런 다음 앱을 엽니다.

    웹 배포를 멘 션 하는 오류가 발생할 경우 웹 배포 설치 단계를 다시 확인 하 고 올바른 포트가 열려 있는지 확인 (서버에서 열려야 8172 포트를 해야 웹 배포).

    앱이 성공적으로 배포 되지만 제대로 실행 되지 않는, 하는 경우 IIS 구성을, ASP.NET 설치 프로그램 또는 웹 사이트 구성에 문제가 있을 수 있습니다. Windows server에서 더 구체적인 오류 메시지에 대 한 IIS에서 웹 사이트 열기 및 한 후 이전 단계를 다시 확인 합니다.
