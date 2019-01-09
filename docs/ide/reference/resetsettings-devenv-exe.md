---
title: -ResetSettings(devenv.exe)
ms.date: 11/16/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 160cbf93cee8ff778a4f84ee833c7fac3d7f26b1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53830666"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings(devenv.exe)

Visual Studio 기본 설정을 복원하고 자동으로 Visual Studio IDE를 시작합니다. 필요에 따라 지정된 *vssettings* 파일로 설정을 다시 설정합니다.

기본 설정은 Visual Studio가 처음 시작될 때 선택된 프로필에 따라 결정됩니다.

> [!TIP]
> IDE(통합된 개발 환경)를 사용하여 설정을 다시 설정하는 방법을 알아보려면 [설정 다시 설정](../environment-settings.md#reset-settings)을 참조하세요.

## <a name="syntax"></a>구문

```cmd
Devenv /ResetSettings SettingsFile
```

## <a name="arguments"></a>인수

`SettingsFile`

Visual Studio에 적용할 *.vssettings* 파일의 전체 경로 및 이름.

일반 개발 설정 프로필을 복원하려면 `General`을 사용합니다.

## <a name="remarks"></a>주의

`SettingsFile`이 지정되지 않은 경우에는 다음 번에 Visual Studio를 시작할 때 기본 설정 컬렉션을 선택하라는 메시지가 표시됩니다.

## <a name="example"></a>예제

다음 명령줄은 `MySettings.vssettings` 파일에 저장된 설정을 적용합니다.

```cmd
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"
```

## <a name="see-also"></a>참고 항목

- [환경 설정](../environment-settings.md)
- [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)
- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)