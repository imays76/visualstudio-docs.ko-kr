---
title: 원격 디버거 다운로드
description: 원격 디버거에 대 한 다운로드 링크
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 491b01d87e4f1a9980143e9ffcc501b3cda7c922
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39189258"
---
1.  장치 또는 서버를 디버그하려는 컴퓨터(대신 Visual Studio를 실행하는 컴퓨터)에 맞는 버전의 원격 도구를 가져옵니다.

    |버전|링크|노트|
    |-|-|-|
    |Visual Studio 2017(최신 버전)|[원격 도구](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|원격 도구의 최신 버전은 모든 Visual Studio 2017 버전과 호환됩니다. 항상 x86, x64 또는 ARM64와 같은 장치의 운영 체제와 일치하는 버전을 다운로드합니다. Windows Server[파일 다운로드를 차단 해제](../../debugger/remote-debugging-unblock-file-download.md)에서 원격 도구를 다운로드하려면 도움말을 참조하세요.|
    |Visual Studio 2015|[원격 도구](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Visual Studio 2015 용 원격 도구 My.VisualStudio.com에서 사용할 수 있습니다. 메시지가 표시 되 면 무료 가입 [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) 프로그램 또는 Visual Studio 구독 ID로 로그인 합니다. Windows Server[파일 다운로드를 차단 해제](../../debugger/remote-debugging-unblock-file-download.md)에서 원격 도구를 다운로드하려면 도움말을 참조하세요.|
    |Visual Studio 2013|[원격 도구](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2013 설명서에서 페이지를 다운로드 합니다.|
    |Visual Studio 2012|[원격 도구](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2012 설명서에서 페이지를 다운로드 합니다.|

2.  다운로드 페이지에서 (x86, x64, ARM 또는 ARM64) 운영 체제와 일치 하는 도구 버전을 선택 하 고 원격 도구를 다운로드 합니다.

    > [!IMPORTANT]
    >  Visual Studio의 릴리스에 대 한 원격 도구의 최신 버전을 설치 하는 것이 좋습니다. 15.8 예를 들어 최신 버전은 이전 버전 (예: 15.0); 호환 그러나 이전 버전 이후 릴리스와의 호환 되지 않습니다. 또한 설치 하려는 운영 체제와 동일한 아키텍처를 가진 원격 도구를 설치 해야 합니다. 즉, 64 비트 운영 체제를 실행 하는 원격 컴퓨터에서 32 비트 응용 프로그램을 디버그 하려는 원격 컴퓨터의 64 비트 버전의 원격 도구를 설치 해야 합니다.
    >
    >  ARM 장치에서 Windows 10에서 디버깅을 위해 원격 도구의 최신 버전으로 제공 되는 ARM64 다운로드를 선택 합니다.  Windows RT 장치에 대 한 Visual Studio 2015 RTW 다운로드에 사용할 수 있는 ARM 버전을 선택 합니다.

3.  실행 파일을 다운로드 했으면, 다음 섹션으로 이동 하 고 설치 지침을 따릅니다.

원격 컴퓨터에 원격 디버거 (msvsmon.exe)를 복사 하 고 실행 하려는 경우는 **원격 디버거 구성 마법사** (**rdbgwiz.exe**) 다운로드 하는 경우에 설치 되는 도구입니다. 특히 원격 디버거를 서비스로 실행 하려는 경우 나중에 구성에 대 한 마법사를 사용 하도록 해야 합니다. 자세한 내용은 [(선택 사항) 원격 디버거를 서비스로 구성](../../debugger/remote-debugging.md#bkmk_configureService)합니다.
