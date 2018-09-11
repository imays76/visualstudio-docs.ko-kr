---
title: 설치 된 앱 패키지 (UWP) 디버그 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 07/17/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.remote.connection
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- app package, debug
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 291f24c6ffdf885cf3d24c5ff163c2f4f911d7ce
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279561"
---
# <a name="debug-an-installed-app-package-in-visual-studio-uwp"></a>Visual Studio (UWP)에 설치 된 앱 패키지 디버그

클릭 하 여 설치 된 앱 패키지를 디버그할 수 있습니다 **디버그 > 기타 디버그 대상 > 디버그 Installed App Package**합니다. 이 디버깅 메서드는 유니버설 Windows 앱 (UWP)에 대 한 이러한 장치에서

* Windows 10 (휴대폰에서 지원 되지 않음)
* XBox
* HoloLens
* IoT

이러한 기능에 대 한 자세한 내용은 블로그 게시물에 대 한 업데이트를 참조 하세요. [설치 된 앱 패키지를 디버깅](https://blogs.msdn.microsoft.com/devops/2016/03/30/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/) 및에서 post [유니버설 Windows 앱 (UWP) 빌드](https://blogs.msdn.microsoft.com/visualstudio/2016/08/02/universal-windows-apps-targeting-windows-10-anniversary-sdk/)합니다.

## <a name="debug-an-installed-app-package-or-running-app-on-a-local-machine-or-device"></a>설치 된 앱 패키지 또는 로컬 컴퓨터 또는 장치에서 실행 중인 앱 디버그

1. UWP 프로젝트를 Visual Studio에서 열고, 클릭 **디버그 > 기타 디버그 대상 > 디버그 Installed App Package**합니다.

2. 선택 **로컬 컴퓨터** 하거나 **장치**합니다.

     선택 하면 **장치**, Windows 10 장치에 컴퓨터를 물리적으로 연결 해야 합니다.

     ![DebugInstalledAppPackage](../debugger/media/debug-installed-app-pkg.png "DebugInstalledAppPackage")

     현재 실행 중인 앱 패키지 표시에서를 설치 합니다 **실행** 노드. 아래에서 위로 표시를 실행 하지 않는 앱 패키지를 설치 **실행 되 고 있지**합니다.

3. 디버깅 하려는 앱의 이름을 선택 **실행** 또는 **실행 되 고 있지** 선택한 **시작** 앱을 이미 실행 중인 경우 또는 **연결**.

     선택 하는 경우 **시작 하지 않음 시작 시 코드를 디버그**, 이렇게 하면 사용자 지정 시간에 시작 하면이 앱에 연결 하려면 Visual Studio 디버거. 제어 경로에서 디버그 하는 효과적인 방법입니다 [다른 시작 방법](/windows/uwp/xbox-apps/automate-launching-uwp-apps), 같은 사용자 지정 매개 변수를 사용 하 여 프로토콜 활성화 합니다.

> [!NOTE]
> Visual Studio를 선택 하 여 모든 실행 중인 UWP 앱 프로세스에 첨부할 수도 **디버그**를 차례로 **프로세스에 연결**합니다. 원래 Visual Studio 프로젝트를 실행 중인 프로세스에 연결할 필요가 되지만 프로세스의 기호 로드에 크게 원본 코드 없는 프로세스를 디버깅 하는 경우 있습니다.
  
## <a name="remote"></a> 원격 컴퓨터에서 설치 또는 실행 중인 앱 디버그 

처음으로 원격 컴퓨터에 설치 된 앱 패키지를 디버깅할 때 Visual Studio는 대상 장치에 원격 도구의 올바른 버전을 설치 합니다. 대상 장치는 Windows 10 컴퓨터, XBox, HoloLens, IoT 장치 여야 합니다.

1. Windows 10 장치에서 사용 하도록 설정 [개발자 모드](/windows/uwp/get-started/enable-your-device-for-development)합니다.

2. 먼저 수동으로 pre-크리에이터 업데이트 버전의 Windows 10을 실행 하는 원격 PC에 연결 하는 경우 [설치 하 고 원격 디버거 시작](../debugger/remote-debugging.md)합니다.

     XBox, HoloLens, IoT 장치를 및 Windows 10 크리에이터 업데이트를 실행 하는 Windows 장치에 대 한 원격 디버거를 수동으로 설치할 필요가 없습니다. 원격 도구 앱을 배포할 때 자동으로 설치 됩니다.

3. 클릭 **디버그 > 기타 디버그 대상 > 설치 된 앱 패키지 디버그**합니다.

4. 첫 번째 드롭다운 목록에서 선택 **원격 컴퓨터**합니다.

5. 이름 또는 연결 하려는 컴퓨터의 IP 주소를 입력 합니다.

     ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

     컴퓨터 이름을 사용 하 여 연결할 수 없습니다 하는 경우 (선택한 후 **시작**), IP 주소를 대신 사용 합니다. XBox, HoloLens, IoT 장치에 대 한 IP 주소를 사용 합니다.

5. 옵션을 선택 하 여 인증 하는 방법 선택 **인증 모드**합니다.

    대부분의 앱에 대 한 기본값을 유지 **유니버설 (암호화 되지 않은 프로토콜)** 합니다.

6. 디버깅 하려는 앱의 이름을 선택 **실행** 또는 **실행 되 고 있지** 선택한 **시작** (에 대 한 실행 중인 응용 프로그램) 또는 **연결**합니다.

     선택 하는 경우 **시작 하지 않음 시작 시 코드를 디버그**, 이렇게 하면 Visual Studio 디버거는 사용자 지정 시간에 시작할 때 앱 패키지를 연결할 수 있습니다. 제어 경로에서 디버그 하는 효과적인 방법입니다 [다른 시작 방법](/windows/uwp/xbox-apps/automate-launching-uwp-apps), 같은 사용자 지정 매개 변수를 사용 하 여 프로토콜 활성화 합니다.

     처음으로 연결된 된 XBox, HoloLens, IoT 장치에서 설치 된 앱 패키지를 디버깅할 때 Visual Studio 원격 디버거 대상 장치에 대 한 올바른 버전을 설치 합니다. 약간의 시간이 걸릴 수 있습니다 하 고 메시지가 표시 됩니다 ``Starting remote debugger`` 이 문제가 발생 하는 동안.

     > [!NOTE]
> 제공 하 고, XBox 또는 HoloLens 장치 디버거가 이미 실행 중인 경우 연결 된 앱을 다시 시작 됩니다.

UWP 앱의 원격 배포에 대 한 고급 옵션에 대 한 자세한 내용은 [배포 및 디버깅 UWP apps]((/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)을 참조 하세요. 
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 디버깅](../debugger/index.md)  
 [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)  
 [원격 디버깅](../debugger/remote-debugging.md)  
 [원격 디버깅을 위해 Windows 방화벽 구성](../debugger/configure-the-windows-firewall-for-remote-debugging.md)  
 [원격 디버거 포트 할당](../debugger/remote-debugger-port-assignments.md)  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)