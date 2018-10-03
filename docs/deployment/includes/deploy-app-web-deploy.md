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
ms.openlocfilehash: 4ef232e64f308699c73c60cbe5b155f1d4ebb725
ms.sourcegitcommit: 1c675dae7c348defb32d9f7ccf7079a1062a1c4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48244114"
---
웹 플랫폼 설치 관리자를 사용 하 여 웹 배포를 설치한 경우 Visual Studio에서 직접 앱을 배포할 수 있습니다.

1. 관리자 권한으로 Visual Studio를 시작 하 고 프로젝트를 다시 엽니다.

    웹 배포를 사용 하 여 앱을 배포 하려면 관리자 권한이 필요 합니다.

1. **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

    게시 프로필을 이전에 구성한 경우 합니다 **게시** 창이 나타납니다. 클릭 **새 프로필**합니다.

1. 에 대 한 **게시 대상 선택**를 선택 **IIS, FTP 등** 클릭 **게시**합니다.

    ![RemoteDBG_Publish_IISl](../../debugger/media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

1. IIS 설정에 대 한 수정 구성 매개 변수를 입력 합니다.

    ![RemoteDBG_Publish_WebDeployl](../../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    유효성을 검사 하려는 경우 호스트 이름을 해결 되지 않으면 다음 단계에서는 합니다 **Server** 텍스트 상자에 IP 주소를 시도 합니다. 포함 `http://` 접두사로 합니다 **Server** 필드입니다.  포트 80을 사용 해야 합니다 **Server** 텍스트 상자의 및 포트 80 및 8172 포트를 방화벽에서 열려 있는지 확인 합니다.

1. 선택할 **유효성 검사**합니다. 연결 설정의 유효성을 검사 하는 경우에 게시를 시도할 수 있습니다.

1. 클릭 **게시** 앱을 게시 합니다.

    출력 탭이 보여줍니다 경우 게시에 성공 하면 브라우저가 그런 다음 앱을 엽니다.

    웹 배포를 멘 션 하는 오류가 발생할 경우 웹 배포 설치 단계를 다시 확인 하 고 올바른 포트가 열려 있는지 확인 (서버에서 열려야 8172 포트를 해야 웹 배포).

    앱이 성공적으로 배포 되지만 제대로 실행 되지 않는, 하는 경우 IIS 구성을, ASP.NET 설치 프로그램 또는 웹 사이트 구성에 문제가 있을 수 있습니다. Windows server에서 더 구체적인 오류 메시지에 대 한 IIS에서 웹 사이트 열기 및 한 후 이전 단계를 다시 확인 합니다.
