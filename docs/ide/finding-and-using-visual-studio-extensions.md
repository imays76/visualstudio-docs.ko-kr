---
title: 확장 찾기 및 사용
ms.date: 06/07/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.ExtensionManager
helpviewer_keywords:
- install extensions
- install packages
- managing extensions visual studio
ms.assetid: 4ca92d93-31b9-47ef-8109-4a429d9e2ca3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d405e84a91570ce1ce7f1e3f32fe72220487b36e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53968132"
---
# <a name="find-and-use-visual-studio-extensions"></a>Visual Studio 확장 찾기 및 사용

Visual Studio 확장은 Visual Studio 내에서 실행되고 새로운 기능 또는 향상된 Visual Studio 기능을 제공하는 코드 패키지입니다. Visual Studio 확장에 대한 자세한 정보는 다음에서 찾을 수 있습니다. [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

**확장 및 업데이트** 대화 상자를 사용하여 웹 사이트 및 다른 위치에서 Visual Studio 확장과 샘플을 설치를 할 수 있으며 사용, 사용 안 함, 업데이트 또는 제거를 할 수 있습니다. (**도구 > 확장 및 업데이트**로 이동하거나 **빠른 실행** 창에 **확장**을 입력합니다). 대화 상자에는 설치된 샘플 및 확장의 업데이트도 표시됩니다. 확장을 웹 사이트에서 다운로드하거나 다른 개발자에게서 얻을 수도 있습니다.

> [!NOTE]
> Visual Studio 2015부터 Visual Studio Marketplace에서 호스트된 확장이 자동으로 업데이트됩니다. **확장 및 업데이트** 대화 상자를 통해 이 설정을 변경할 수 있습니다.  자세한 내용은 아래에서 **자동 확장 업데이트** 에 대한 단원을 참조하세요.

## <a name="finding-visual-studio-extensions"></a>Visual Studio 확장 찾기

[Visual Studio Marketplace](https://marketplace.visualstudio.com/vs)에서 확장을 설치할 수 있습니다. 확장은 Visual Studio에 기능을 추가하는 제어, 샘플, 템플릿 또는 기타 구성 요소일 수 있습니다. Visual Studio는 VSIX 패키지 형식에서 프로젝트 템플릿, 항목 템플릿, **도구 상자** 항목, MEF(Managed Extension Framework) 구성 요소 및 VSPackage 등의 확장을 지원합니다. MSI 기반 확장도 다운로드하고 설치할 수 있지만 **확장 및 업데이트** 대화 상자에서 해당 확장을 사용하거나 사용하지 않도록 설정할 수 없습니다. isual Studio Marketplace 에는 VSIX 및 MSI 확장이 모두 포함되어 있습니다.

## <a name="installing-or-uninstalling-visual-studio-extensions"></a>Visual Studio 확장 설치 또는 제거

**확장 및 업데이트**에서 설치하려는 확장을 찾습니다. (확장의 이름이나 이름 일부를 알고 있는 경우 **검색** 창에서 검색할 수 있습니다.) **다운로드**를 클릭합니다.  확장이 설치를 위해 예약됩니다. Visual Studio의 모든 인스턴스를 닫으면 확장이 설치됩니다.

종속성이 포함된 확장을 설치하려고 하면 설치 관리자에서 이미 설치가 되었는지 여부를 확인합니다. 설치가 되어 있지 않으면, **확장 및 업데이트** 대화 상자 목록은 확장을 설치하기 전에 설치해야 하는 종속성을 나열합니다.

확장의 사용을 중지하려는 경우 사용하지 않도록 설정하거나 제거합니다. 확장을 사용하지 않으면 설치되어 있지만 로드되지 않습니다. VSIX 확장만 사용하지 않도록 설정할 수 있습니다. MSI를 사용하여 설치된 확장만 제거할 수 있습니다. 확장을 찾고 **제거** 또는 **사용 안 함**을 클릭합니다. 사용하지 않도록 설정된 확장을 언로드하려면 Visual Studio를 다시 시작해야 합니다.

## <a name="per-user-and-administrative-extensions"></a>사용자별 및 관리 확장

대부분의 확장은 *%LocalAppData%\Microsoft\VisualStudio\\<Visual Studio 버전\>\Extensions\\* 폴더에 설치된 사용자별 확장입니다. 몇몇 확장은 *\<Visual Studio 설치 폴더>\Common7\IDE\Extensions\\* 폴더에 설치된 관리 확장입니다.

오류 또는 악의적인 코드를 포함할 수 있는 확장으로부터 시스템을 보호하기 위해, Visual Studio가 일반 사용자 권한으로 실행되는 경우에만 로드되도록 사용자별 확장을 제한할 수 있습니다. 이는 Visual Studio가 관리자 권한으로 실행되는 경우에는 사용자별 확장을 사용하지 않도록 설정됨을 의미합니다. 이 작업을 수행하려면 **확장 및 업데이트** 옵션 페이지로 이동합니다(**도구 > 옵션** > **환경** > **확장 및 업데이트**로 이동하거나 **빠른 실행** 창에서 **확장** 을 입력함). **관리자로 실행할 때 사용자 확장별 로드** 확인란을 선택 취소한 다음 Visual Studio를 다시 시작합니다.

## <a name="automatic-extension-updates"></a>자동 확장 업데이트

Visual Studio Marketplace에서 새 버전을 사용할 수 있으면 사용자 단위 확장이 자동으로 업데이트됩니다.  새 버전의 확장이 검색되어 백그라운드로 설치되면 다음에 Visual Studio를 다시 시작할 때 새 버전의 확장이 실행됩니다.

사용자 단위 확장만 자동으로 업데이트됩니다.  모든 사용자에 대해 설치되는 관리 확장은 업데이트되지 않으므로 새 버전을 계속 **확장 및 업데이트** 대화 상자 **업데이트** 노드를 통해 수동으로 설치합니다. **확장 및 업데이트** 대화 상자의 확장 세부 정보 창에서 자동으로 업데이트되는 확장을 볼 수 있습니다.

자동 업데이트를 사용하지 않도록 설정하려는 경우 해당 기능을 모든 확장에 대해 사용하지 않도록 설정할 수도 있고 특정 확장에 대해서만 사용하지 않도록 설정할 수도 있습니다.

- 모든 확장에 대해 자동 업데이트를 사용하지 않도록 설정하려면 **확장 및 업데이트** 대화 상자에서 **확장 및 업데이트 설정 변경** 링크를 선택하고 **자동으로 확장 업데이트**의 선택을 취소합니다.

- 특정 확장에 대해 자동 업데이트를 사용하지 않도록 설정하려면 **확장 및 업데이트** 대화 상자 오른쪽에 있는 확장 세부 정보 창에서 **자동으로 이 확장 업데이트** 옵션의 선택을 취소합니다.

> [!NOTE]
> Visual Studio 2015 업데이트 2부터 사용자별 확장, 모든 사용자 확장 또는 둘 다(기본 설정)에 대해 자동 업데이트를 사용할지를 지정할 수 있습니다(**도구 > 옵션 > 환경 > 확장 및 업데이트**).

## <a name="extension-crashunresponsiveness-notifications"></a>확장 크래시/무응답 알림

**Visual Studio 2017 버전 15.3**의 새로운 기능으로, Visual Studio는 확장이 이전 세션 중 발생한 크래시와 관련된 것으로 의심되는 경우 사용자에게 알립니다. Visual Studio의 작동이 중단되면 Visual Studio에서는 예외 스택을 저장합니다. 다음번에 Visual Studio가 시작되면 Visual Studio에서는 리프로 시작하고 베이스로 진행하여 스택을 검사합니다. Visual Studio에서는 프레임이 설치되고 사용하도록 설정된 확장의 일부인 모듈에 속한다고 판단할 경우 알림을 표시합니다.

**Visual Studio 2017 버전 15.6**의 새로운 기능으로, Visual Studio는 확장으로 인해 UI가 응답하지 않는다고 의심되는 경우 사용자에게 알립니다.

이러한 알림이 표시되면 알림을 무시하거나 다음 작업 중 하나를 수행할 수 있습니다.

- **이 확장을 사용 안 함**을 선택합니다. Visual Studio에서는 확장을 사용하지 않도록 설정하고 이 설정을 적용하기 위해 시스템을 다시 시작해야 할지 여부를 알립니다. 원하는 경우 **확장 및 업데이트** 대화 상자에서 확장을 다시 사용하도록 설정할 수 있습니다.

- **이 메시지를 다시 표시 안 함**을 선택합니다.
  - 알림이 이전 세션의 크래시와 관련된 경우 Visual Studio는 이 확장에 연결된 크래시가 발생할 때 더 이상 알림을 표시하지 않습니다. Visual Studio는 무응답이 이 확장에 연결될 수 있는 경우 또는 다른 확장에 연결될 수 있는 크래시나 무응답의 경우에는 알림을 계속 표시합니다.
  - 알림이 무응답과 관련된 경우 IDE는 이 확장이 무응답에 연결된 경우 더 이상 알림을 표시하지 않습니다. Visual Studio는 이 확장의 경우 크래시 관련 알림을 표시하고 다른 확장의 경우 크래시 및 무응답 관련 알림을 표시합니다.

- 이 페이지를 확인하려면 **자세한 정보**를 선택합니다.

- 알림 끝에서 **X** 단추를 선택하여 알림을 해제합니다. 크래시 또는 UI 무응답에 연결된 확장의 미래 인스턴스에 대해 새 알림이 표시됩니다.

> [!NOTE]
> UI 무응답 또는 크래시 알림은 UI가 응답하지 않거나 크래시가 발생한 경우 확장 모듈 중 하나가 스택에 있었음을 의미할 뿐입니다. 확장 자체가 원인이라는 의미가 아닐 수 있습니다. 확장이 Visual Studio의 일부인 코드를 호출했고 이로 인해 UI 무응답 또는 크래시가 발생했을 수 있습니다. 그러나 UI 무응답 또는 크래시를 유발한 확장이 중요하지 않을 경우 알림이 유용할 수 있습니다. 이 경우 확장을 사용하지 않도록 설정하면 생산성에 영향을 미치지 않고 이후에 UI 무응답 또는 크래시를 피할 수 있습니다.

## <a name="sample-master-copies-and-working-copies"></a>샘플 마스터 복사본 및 작업 복사본

온라인 샘플을 설치하면 솔루션은 다음 두 위치에 저장됩니다.

- 작업 복사본은 **새 프로젝트** 대화 상자에 지정된 위치에 저장됩니다.

- 별도의 마스터 복사본은 컴퓨터에 저장됩니다.

**확장 및 업데이트** 대화 상자를 사용하여 이러한 샘플 관련 작업을 수행할 수 있습니다.

- 설치한 샘플의 마스터 복사본을 나열합니다.

- 샘플의 마스터 복사본을 사용하지 않거나 제거합니다.

- 기술이나 기능과 관련된 샘플의 모음인 샘플 팩을 설치합니다.

- 개별 온라인 샘플을 설치합니다. ( **새 프로젝트** 대화 상자에서도 할 수 있습니다.)

- 설치된 샘플에 대해 소스 코드 변경 내용이 게시되면 업데이트 알림을 봅니다.

- 업데이트 알림이 있는 경우 설치된 샘플의 마스터 복사본을 업데이트합니다.

## <a name="installing-without-using-the-extensions-and-updates-dialog-box"></a>확장 및 업데이트 대화 상자를 사용하지 않고 설치

*.vsix* 파일에 패키지된 확장은 Visual Studio Marketplace 이외의 위치에서 사용될 수 있습니다. **확장 및 업데이트** 대화 상자는 이러한 파일을 검색할 수 없지만, *.vsix* 파일을 두 번 클릭하거나 이 파일을 선택하고 **Enter** 키를 눌러 해당 파일을 설치할 수 있습니다. 그런 다음, 지침을 따르세요. 확장이 설치되면 **확장 및 업데이트** 대화 상자를 사용하여 사용, 사용 안 함으로 설정하거나 제거할 수 있습니다.

## <a name="extension-types-not-supported-by-the-extensions-and-updates-dialog-box"></a>확장 및 업데이트 대화 상자에서 지원되지 않는 확장 형식

Visual Studio에서는 Microsoft Installer(MSI)에 의해 설치되는 확장은 계속 지원하지만 수정 없이 **확장 및 업데이트** 대화 상자를 통해 설치되는 확장은 지원하지 않습니다.

> [!TIP]
> MSI 기반 확장은 *extension.vsixmanifest* 파일을 포함하는 경우 **확장 및 업데이트** 대화 상자에 나타납니다.