---
title: -Out(devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- errors [Visual Studio], builds
- Devenv, /out switch
- builds [Visual Studio], logs
- error logs [Visual Studio], command-line build errors
- error logs [Visual Studio]
- /out Devenv switch
- out Devenv switch
- builds [Visual Studio], errors
- output files, build errors
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f240b464ddba4e0549e3faff432685201e4560f6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985643"
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)
솔루션을 실행, 빌드, 다시 빌드 또는 배포하는 경우 오류를 저장하고 표시할 파일을 지정합니다.

## <a name="syntax"></a>구문

```cmd
devenv /out FileName
```

## <a name="arguments"></a>인수
 `FileName`

 필수 요소. 실행 파일을 빌드할 때 오류를 수신할 파일의 경로 및 이름입니다.

## <a name="remarks"></a>주의
 존재하지 않는 파일 이름을 지정하는 경우 파일이 자동으로 만들어집니다. 파일이 이미 있는 경우 결과는 파일의 기존 내용에 추가됩니다.

 명령줄 빌드 오류는 **명령** 창 및 **출력** 창의 솔루션 작성기 보기에 표시됩니다. 이 옵션은 무인 빌드를 실행하고 결과를 봐야 하는 경우에 유용합니다.

## <a name="example"></a>예제
 이 예제에서는 `MySolution`을 실행하고 `MyErrorLog.txt` 파일에 오류를 기록합니다.

```cmd
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"
```

## <a name="see-also"></a>참고 항목

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)
- [/Run(devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Deploy (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)