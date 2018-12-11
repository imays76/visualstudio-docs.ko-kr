---
title: 미리 보기 릴리스 설치
description: Mac용 Visual Studio 2019 미리 보기를 포함하여 Mac용 Visual Studio를 업데이트하고 미리 보기 릴리스에 액세스하는 방법에 대한 지침입니다.
zone_pivot_groups: mac-ide-version
author: conceptdev
ms.author: crdun
ms.date: 11/03/2018
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 0E1EF257-9DE4-4653-9DF4-805CE007A1A1
ms.openlocfilehash: b5eea8c2c894b7eeaa13c83ae6698d1297de9297
ms.sourcegitcommit: ae46be4a2b2b63da7e7049e9ed67cd80897c8102
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2018
ms.locfileid: "52896759"
---
# <a name="install-a-preview-release"></a>미리 보기 릴리스 설치

::: zone pivot="vsmac2019"

> [!TIP]
> 이제 Mac용 Visual Studio 2019 미리 보기를 사용할 수 있습니다. 최초로 안정적인 Mac용 Visual Studio 릴리스와 병렬로 설치할 수 있습니다.

## <a name="requirements-for-the-visual-studio-2019-for-mac-preview"></a>Mac용 Visual Studio 2019 미리 보기의 요구 사항

* macOS Sierra 10.13 이상이 설치된 Mac

iOS 또는 macOS용 Xamarin 앱을 빌드하려면 다음 항목도 필요합니다.

* Xcode 10.0 이상 대개 안정적인 최신 버전을 사용하는 것이 좋습니다.
* Apple ID. Apple ID가 없으면 https://appleid.apple.com에서 새로 만들 수 있습니다. Xcode를 설치하고 서명하려면 Apple ID가 있어야 합니다.

## <a name="installing-the-preview"></a>미리 보기 설치

1. [Mac용 Visual Studio 미리 보기 페이지](https://aka.ms/vs4mac-preview)에서 미리 보기 설치 관리자를 다운로드합니다.
2. 다운로드가 완료되면 **VisualStudioforMacPreviewInstaller.dmg**를 클릭하여 설치 관리자를 탑재한 다음, 화살표 로고를 두 번 클릭하여 설치 관리자를 실행합니다.

    [![설치를 시작하려면 큰 화살표를 클릭](media/install-preview-installer-sml.png)](media/install-preview-installer.png#lightbox)

3. 인터넷에서 애플리케이션이 다운로드된다는 경고가 표시될 수 있습니다. **열기**를 클릭합니다.
4. 설치 관리자가 시스템을 확인할 때까지 기다립니다.

    [![설치 관리자가 구성 요소를 설치할 시스템 확인](media/install-preview-checking-sml.png)](media/install-preview-checking.png#lightbox)

5. 개인 정보 및 라이선스 조건에 동의하라는 경고가 나타납니다. 링크가 안내하는 문서를 잘 읽고, 동의하면 **계속**을 누릅니다.

    [![개인 정보 및 조건 링크를 클릭한 다음, 동의하면 계속 진행](media/install-preview-privacy-sml.png)](media/install-preview-privacy.png#lightbox)

6. 사용 가능한 워크로드 목록이 표시됩니다. 사용할 워크로드를 선택합니다.

    [![설치할 워크로드 기능 선택](media/install-preview-selection-sml.png)](media/install-preview-selection.png#lightbox)

    현재 사용하는 Mac용 Visual Studio 2017 버전이 7.7보다 낮으면 안정적인 최신 버전(병렬 설치를 지원하려면 필요)으로 업그레이드하는 것을 승인해 달라는 메시지가 나타납니다. **계속**을 눌러 업그레이드를 승인합니다.

    ![안정적인 버전 7.7로 업그레이드 필요](media/install-preview-older-upgrade.png)

7. 원하는 항목을 선택한 후 **설치** 단추를 누릅니다.
8. 설치 관리자는 Mac용 Visual Studio 및 사용자가 선택한 워크로드를 다운로드하고 설치하는 동안 진행률을 표시합니다. 설치에 필요한 권한을 부여하려면 암호를 입력하라는 메시지가 표시될 수 있습니다.
9. 언제든지 미리 보기 버전을 테스트하고 싶을 때 **Visual Studio(미리 보기)** 를 사용하거나, 프로덕션 작업에 필요한 안정적인 최신 Visual Studio로 다시 전환할 수 있습니다. 다음 두 아이콘이 여기에 표시됩니다.

    ![안정적인 버전과 미리 보기 아이콘의 차이점](media/install-preview-icons-sml.png)

회사 환경에 설치하는 동안 네트워크 문제가 있는 경우 [방화벽 또는 프록시 뒤에 설치](https://docs.microsoft.com/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server) 지침을 검토하세요.

[릴리스 정보](https://docs.microsoft.com/visualstudio/releasenotes/vs2019-mac-preview-relnotes)의 변경 내용에 대해 자세히 알아보세요.

::: zone-end
::: zone pivot="vsmac2017"

## <a name="install-an-update-for-visual-studio-2017-for-mac"></a>Mac용 Visual Studio 2017 업데이트 설치

Mac용 Visual Studio의 새 버전이 공식적으로 릴리스되기 전에 미리 보기로 사용할 수 있습니다. 미리 보기 릴리스에서는 새로운 기능이 제품에 완전히 통합되기 전에 사용해 보고 버그 수정을 받을 수 있습니다.

Mac용 Visual Studio에 대한 미리 보기 릴리스는 별도 다운로드가 아닌 업데이트 형태로 배포됩니다. Mac용 visual Studio에는 [업데이트](update.md) 문서에서 설명한 대로 안정성, 베타 및 알파 등의 세 업데이트 채널이 있습니다.

대부분의 미리 보기 릴리스는 **베타**와 **알파** 채널을 통해 제공되지만 가장 정확한 정보를 받을 수 있도록 [미리 보기 릴리스 정보](/visualstudio/releasenotes/vs2017-mac-preview-relnotes)를 항상 확인합니다. 

Mac용 Visual Studio의 미리 보기를 설치하려면 다음 단계를 사용합니다.

1. **Visual Studio > 업데이트 확인**으로 이동합니다.
2. 업데이트 채널 콤보 상자에서 **베타**를 선택합니다.
3. **채널 전환** 단추를 선택하여 선택한 채널로 전환하고 새 업데이트 다운로드를 시작합니다.
4. **업데이트 다시 시작 및 설치** 단추를 선택하여 업데이트 설치를 시작합니다.

Mac용 Visual Studio에서 업데이트에 대한 자세한 내용은 [업데이트](update.md) 문서를 참조하세요.

::: zone-end