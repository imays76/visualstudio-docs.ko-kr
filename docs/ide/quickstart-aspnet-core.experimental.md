---
title: Visual Studio를 사용하여 C#으로 ASP.NET Core 웹앱 만들기
description: C# 및 ASP.NET Core를 사용하여 단계별로 Visual Studio에서 간단한 Hello World 웹앱을 만드는 방법을 알아봅니다.
ms.custom: mvc
ms.date: 07/30/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 4462edff04933dfcb3d334a841982ff0406270ba
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42626938"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>빠른 시작: Visual Studio를 사용하여 첫 번째 ASP.NET Core 웹앱 만들기

이 5~10분 진행되는 Visual Studio를 사용하는 방법에 대한 소개에서 ASP.NET 프로젝트 템플릿과 C# 프로그래밍 언어를 사용하여 간단한 "Hello World" 웹앱을 만듭니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기

먼저, ASP.NET Core 웹 응용 프로그램 프로젝트를 만듭니다. 방법은 다음과 같습니다.

1. Visual Studio 2017을 엽니다.

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 차례로 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual C#** 을 확장하고 **.NET Core**를 선택합니다. 가운데 창에서 **ASP.NET Core 웹 응용 프로그램**을 선택합니다. 그런 다음, 파일 이름을 `HelloWorld`로 지정하고 **확인**을 선택합니다.

1. **새 ASP.NET Core 웹 응용 프로그램** 대화 상자의 위쪽 드롭다운 메뉴에 **ASP.NET Core 2.0** 이 표시되는지 확인합니다. 그런 다음, **웹 응용 프로그램**을 선택하고 **확인**을 선택합니다.

  ![Visual Studio에서 C# ASP.NET Core 프로젝트를 만드는 방법을 보여주는 애니메이션 처리된 .gif 파일 보기](../ide/media/csharp-aspnet-animated-create-project.gif)

  곧 Visual Studio에서 프로젝트 파일이 열립니다.

   > [!NOTE]
   > **.NET Core** 프로젝트 템플릿 범주가 표시되지 않으면 왼쪽 창에서 **Visual Studio 설치 관리자 열기** 링크를 선택합니다.
   >
   > ![새 프로젝트 대화 상자에서 Visual Studio 설치 관리자 열기](../ide/media/open-visual-studio-installer.png)
   >
   > Visual Studio 설치 관리자가 시작됩니다. **ASP.NET 및 웹 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.
   >
   > ![VS 설치 관리자에서 ASP.NET 워크로드](../ide/media/quickstart-aspnet-workload.png)
   >
   > (새 워크로드를 계속 설치하려면 먼저 Visual Studio를 닫아야 할 수 있습니다.)

## <a name="create-and-run-the-app"></a>앱 만들기 및 실행

다음으로, "Hello World" 웹앱을 만들고 실행합니다. 방법은 다음과 같습니다.

1. **솔루션 탐색기**에서 **Pages** 폴더를 확장한 다음, **About.cshtml**을 선택합니다.

   이 파일은 웹앱에서 이름이 **정보**로 이름이 지정된 페이지에 해당합니다.

   ![웹앱의 정보 페이지](../ide/media/csharp-aspnet-about-page.png)

1. “추가 정보” 텍스트를 “**Hello World!**”로 변경합니다.

1. **솔루션 탐색기**에서 **About.cshtml**을 확장한 다음, **About.cshtml.cs**를 선택합니다.

1. “응용 프로그램 설명” 메시지 텍스트를 “**내 메시지란?**”으로 변경합니다.

1. **IIS Express**를선 택하거나 **Ctrl**+**F5**를 눌러 앱을 실행하고 웹 브라우저에서 엽니다.

  ![Visual Studio에서 C# ASP.NET Core 웹앱을 만들고 실행하는 방법을 보여주는 애니메이션 처리된 .gif 파일 보기](../ide/media/csharp-aspnet-animated-hello-world.gif)

   > [!NOTE]
   > **‘IIS Express’ 웹 서버에 연결할 수 없습니다**라는 오류 메시지가 발생하면 Visual Studio를 닫은 후 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 **관리자 권한으로 실행** 옵션을 사용하여 엽니다. 그런 다음 응용 프로그램을 다시 실행합니다.

1. **정보** 페이지에 업데이트된 텍스트가 포함되는지 확인합니다.

1. 웹 브라우저를 닫습니다.

이 빠른 시작을 완료한 것을 축하 드립니다! C#, ASP.NET Core 및 Visual Studio IDE(통합 개발 환경)를 이해하는 데 도움이 되었기를 바랍니다.

## <a name="next-steps"></a>다음 단계

자세히 알아보려면 계속 다음 자습서를 사용하세요.

> [!div class="nextstepaction"]
> [Visual Studio에서 C# 및 ASP.NET 시작](tutorial-csharp-aspnet-core.md)

## <a name="see-also"></a>참고 항목

[Visual Studio를 사용하여 Azure App Service에 웹앱 게시](..//deployment/quickstart-deploy-to-azure.md)
