---
title: SharePoint 솔루션 개발을 위한 요구 사항 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, prerequisites
- SharePoint development in Visual Studio, requirements
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9c9d6a726b290bfed1c086f9fb03290a37c91490
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37119400"
---
# <a name="requirements-for-developing-sharepoint-solutions"></a>SharePoint 솔루션 개발을 위한 요구 사항
Visual Studio에 포함 된 SharePoint 솔루션 개발 도구를 사용 하려면 먼저 시스템에 다음 필수 구성 요소를 설치 해야 합니다.

- C# 및/또는 Visual Basic 또는 버전의 Visual Studio 응용 프로그램 수명 주기 관리 (ALM)를 사용 하 여 visual Studio입니다.

- [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 64 비트 설치 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] 또는 64 비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2.

     또는

- [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 64 비트 설치 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] 또는 64 비트 [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2.

> [!NOTE]
> 서버 운영 체제 에서만 SharePoint에서 공식적으로 지원 되지만, 두 클라이언트 운영 체제 수: [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 고 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] SP1. 자세한 내용은 [SharePoint Server 2010 개발자 워크스테이션 설치 가이드](http://go.microsoft.com/fwlink/?LinkID=164557)합니다.

비즈니스 데이터 연결 (BDC) 모델 프로젝트 형식에서는 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 시스템에 설치할 수 있습니다.

Visual Studio에서 SharePoint 솔루션을 개발 하려면 Visual Studio와 동일한 컴퓨터에 SharePoint를 설치 해야 합니다. SharePoint 개발자 도구는 SharePoint 독립 실행형 구성;만 지원 되는 또한 팜 (원격) 구성을 지원 하지 않습니다.

> [!NOTE]
> Visual Studio에서 SharePoint 프로젝트만 지원 [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)]합니다. 선택 하는 경우 [!INCLUDE[net_v40_long](../sharepoint/includes/net-v40-long-md.md)] 새 SharePoint 프로젝트의 경우 여전히 대상 [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)]합니다.

설치 하는 방법에 대 한 자세한 내용은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 참조 하세요 [Visual Studio 설치](../install/install-visual-studio.md)합니다.

## <a name="vista-and-windows-7-user-account-control-uac"></a>Vista 및 Windows 7 UAC (사용자 계정 컨트롤)
[!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 및 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 로 사용자 계정 컨트롤 (UAC) 라고 하는 보안 기능을 통합 합니다. SharePoint 솔루션을 개발 하 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] 하 고 [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] 시스템의 경우 UAC를 실행 해야 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 시스템 관리자로 합니다. 바탕 화면에서 바로 가기 메뉴를 열고 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 선택한 후 **관리자 권한으로 실행**합니다.

항상 관리자 권한으로 실행 하려면 바탕 화면 바로 가기의 구성 하려면 해당 바로 가기 메뉴를 열고, 선택 **속성**를 선택 합니다 **고급** 단추를 선택한 다음는 **관리자 권한으로 실행**  확인란 합니다.

자세한 내용은 [이해 및 Windows Vista의 사용자 계정 컨트롤 구성](http://go.microsoft.com/fwlink/?LinkID=156476)합니다. 및 [Windows 7 사용자 계정 컨트롤](http://go.microsoft.com/fwlink/?LinkId=177523)합니다.

## <a name="sharepoint-permissions-considerations"></a>SharePoint 사용 권한 고려 사항
SharePoint 솔루션을 개발 하려면 실행 하 고 SharePoint 솔루션을 디버깅할 충분 한 권한이 있어야 합니다. SharePoint 솔루션을 테스트할 수 있습니다, 전에 필요한 권한이 있는지 확인 하려면 다음 단계를 수행 합니다.

1. 시스템에서 관리자 권한으로 사용자 계정을 추가 합니다.

2. 팜 관리자는 SharePoint 서버에 대 한 사용자 계정에 추가 합니다.

    1. SharePoint 중앙 관리에서 선택 합니다 **팜 관리자 그룹 관리** 링크 합니다.

    2. 에 **Farm Administrators** 페이지를 선택 합니다 **새로 만들기** 단추.

3. 사용자 계정에 추가 된 권한을 WSS_ADMIN_WPG 그룹에 있습니다.

## <a name="see-also"></a>참고자료
[시작 &#40;Visual Studio에서 SharePoint 개발&#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)
