---
title: -UseEnv(devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VC.Project.UseEnvVars.ExcludePath
- VC.Project.UseEnvVars.LibraryPath
- VC.Project.UseEnvVars.SourcePath
- VC.Project.UseEnvVars.Include
- VC.Project.UseEnvVars.Path
- VC.Project.UseEnvVars.ReferencePath
helpviewer_keywords:
- UseEnv switch
- /UseEnv Devenv switch
- Devenv, /UseEnv
ms.assetid: 2dd14603-a61b-42d2-ba31-427a0ee8a799
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a11d8eceec682e37f9bf34c79980c37880bdbe6
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948493"
---
# <a name="useenv-devenvexe"></a>/UseEnv(devenv.exe)

Visual Studio를 시작하고 환경 변수를 **VC++ 디렉터리** 대화 상자에 로드합니다.

> [!NOTE]
> **C++ 워크로드로 데스크톱 개발**을 사용하여 이 스위치를 설치합니다.

## <a name="syntax"></a>구문

```shell
Devenv /useenv
```

## <a name="example"></a>예

다음 예제에서는 Visual Studio를 시작하고 환경 변수를 **VC++ 디렉터리** 대화 상자에 로드합니다.

```shell
Devenv.exe /useenv
```

## <a name="see-also"></a>참고 항목

* [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)