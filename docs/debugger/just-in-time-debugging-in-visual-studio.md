---
title: 방법:-Just-in-time 디버거에 응답 | Microsoft Docs
ms.custom: ''
ms.date: 05/23/17
ms.technology: vs-ide-debug
ms.topic: troubleshooting
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fd3f565d8bb58ae290b0b569bb61d4cb57e8edaa
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179777"
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>방법:-Just-in-time 디버거에 응답

시간에만 표시 하는 경우 수행 해야 하는 작업을 수행 하려는 따라 달라 집니다 디버거 대화 상자:

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>수정 하거나 (Visual Studio 사용자) 오류를 디버깅 하려는 경우

- 있어야 [Visual Studio가 설치 되어](http://visualstudio.microsoft.com) 디버그 하려고 하는 오류에 대 한 자세한 정보를 보려면. 자세한 내용은 [Just-In-Time 디버거를 사용 하 여 디버그](../debugger/debug-using-the-just-in-time-debugger.md)합니다. 오류를 해결 하 고 앱 수 없습니다, 오류를 해결 하려면 앱의 소유자에 게 문의 합니다.

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>Just-In-Time 디버거 대화 상자를 표시 하지 못하도록 하려는 경우

시간에 것을 방지 하기 위해 취할 수 있습니다 디버거 대화 상자가 표시 됩니다. 응용 프로그램 오류를 처리 하는 경우 일반적으로 앱을 실행할 수 있습니다.

1. (웹 앱) 웹 앱을 실행 하려는 경우 스크립트 디버깅을 비활성화할 수 있습니다.

    Internet Explorer 또는 Edge에 대 한 인터넷 옵션 대화 상자에서 스크립트 디버깅을 사용 하지 않도록 합니다. 이러한 설정에 액세스할 수 있습니다 합니다 **Control Panel** > **네트워크 및 인터넷** > **인터넷 옵션** (정확한 단계는 종속 프로그램 버전의 Windows 및 브라우저)입니다.

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    오류가 있는 웹 페이지를 다시 여십시오. 이 설정을 변경 하는 경우에 문제가 해결 되지 않으면, 문제를 해결 하려면 웹 앱의 소유자에 게 문의 합니다.

3. (Visual Studio 사용자) 경우 Visual Studio가 설치 (또는 설치한 경우 이전에 설치 및 제거)를 설치한 [사용 하지 않도록 설정 하면 시간 디버깅](../debugger/debug-using-the-just-in-time-debugger.md) 앱을 다시 실행 해 보세요.

    > [!IMPORTANT]
    > Just in Time을 사용 하지 않도록 설정 하는 경우 디버깅 및 앱에서 처리 되지 않은 예외 (오류), 표준 오류 대화 상자를 대신 참조 하거나 됩니다 또는 앱 작동이 중단 되거나 중지 됩니다. 앱 (사용자 또는 앱의 소유자)가 오류를 해결할 때까지 정상적으로 실행 되지 않습니다.

2. (ASP.NET 및 IIS) IIS에서 ASP.NET 웹 앱을 호스트 하는 경우 서버 쪽 디버깅이 사용 하지 않도록 설정 합니다.

    IIS 관리자에서 서버 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **기능 보기로 전환**합니다. ASP.NET 섹션에서 선택 **.NET 컴파일** 한 다음 선택 했는지 확인 하 고 **False** (단계는 이전 버전의 IIS 다릅니다) 디버그 동작으로 합니다.

## <a name="see-also"></a>참고 항목
 [디버거 기본 사항](../debugger/getting-started-with-the-debugger.md)
