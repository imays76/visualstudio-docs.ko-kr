---
title: Visual Studio에서 C# 및 ASP.NET Core 시작
description: C#을 사용하여 단계별로 Visual Studio에서 ASP.NET Core 웹앱을 만드는 방법을 알아봅니다.
ms.custom: ''
ms.date: 08/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: fb1532a76d9bc530146ba5a0f563bcaa9389226c
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42627114"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>자습서: Visual Studio에서 C# 및 ASP.NET Core 시작

Visual Studio를 사용하여 ASP.NET Core로 C#을 개발하기 위한 이 자습서에서는 C# ASP.NET Core 웹앱을 만들고, 해당 앱을 변경하며, IDE의 일부 기능을 살펴보고, 앱을 실행합니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기

먼저 ASP.NET Core 프로젝트를 만들 것입니다. 아무 것도 추가하지 않아도 웹 사이트에 필요한 모든 템플릿 파일과 함께 프로젝트 형식이 제공됩니다.

1. Visual Studio 2017을 엽니다.

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 차례로 선택합니다. 

3. 왼쪽 창의 **새 프로젝트** 대화 상자에서 **Visual C#**, **Web**을 차례로 확장한 후 **.NET Core**를 선택합니다. 가운데 창에서 **ASP.NET Core 웹 응용 프로그램**을 선택합니다. 그런 다음, 파일 이름을 *MyCoreApp*으로 지정하고, **확인**을 선택합니다.

   ![Visual Studio IDE의 새 프로젝트 대화 상자의 ASP.NET Core 웹 응용 프로그램 프로젝트 템플릿](../ide/media/csharp-aspnet-choose-template-name-mycoreapp-mvc.png)

### <a name="add-a-workload-optional"></a>(선택 사항) 워크로드 추가

**ASP.NET Core 웹 응용 프로그램** 프로젝트 템플릿이 표시되지 않는 경우, **ASP.NET 및 웹 개발** 워크로드를 추가하여 얻을 수 있습니다. 컴퓨터에 Visual Studio 2017 업데이트가 설치되었는지 여부에 따라 다음 두 방법 중 하나로 이 워크로드를 추가할 수 있습니다.

#### <a name="option-1-use-the-new-project-dialog-box"></a>옵션 1: 새 프로젝트 대화 상자 사용

1. **새 프로젝트** 대화 상자에서 **Visual Studio 설치 관리자 열기** 링크를 선택합니다.

   ![새 프로젝트 대화 상자에서 Visual Studio 설치 관리자 열기 링크 선택](../ide/media/vs-open-visual-studio-installer-generic.png)

1. Visual Studio 설치 관리자가 시작됩니다. **ASP.NET 및 웹 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

   ![Visual Studio Installer에서 .NET Core 플랫폼 간 개발 워크로드](../ide/media/quickstart-aspnet-workload.png)

   (새 워크로드를 계속 설치하려면 먼저 Visual Studio를 닫아야 할 수 있습니다.)

#### <a name="option-2-use-the-tools-menu-bar"></a>옵션 2: 도구 메뉴 모음 사용

1. **새 프로젝트** 대화 상자에서 취소합니다. 그런 다음, 상단 메뉴 모음에서 **도구** > **도구 및 기능 가져오기**를 선택합니다.

1. Visual Studio 설치 관리자가 시작됩니다. **ASP.NET 및 웹 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

   (새 워크로드를 계속 설치하려면 먼저 Visual Studio를 닫아야 할 수 있습니다.)

### <a name="add-a-project-template"></a>프로젝트 템플릿 추가

1. **새 ASP.NET Core 웹 응용 프로그램** 대화 상자에서 **웹 응용 프로그램모델-뷰-컨트롤러)** 프로젝트 템플릿을 선택합니다.

1. 상단 드롭다운 메뉴에 **ASP.NET Core 2.0**이 표시되는지 확인합니다. 그런 다음, **확인**을 선택합니다.

   ![새 ASP.NET Core 웹 응용 프로그램 대화 상자](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>솔루션 정보

이 솔루션은 앱을 다음과 같이 세 가지 주요 구성 요소로 구분하는 MVC(모델-뷰-컨트롤러) 아키텍처 패턴을 따릅니다. 

* **M(모델)** 은 앱 데이터를 나타내는 클래스를 포함합니다. 모델 클래스는 유효성 검사 논리를 사용하여 해당 데이터의 비즈니스 규칙을 적용합니다. 일반적으로 모델 개체는 모델 상태를 검색하고 데이터베이스에 저장합니다.
* **V(뷰)** 는 앱의 UI(사용자 인터페이스)를 표시하는 구성 요소입니다. 일반적으로 이 UI는 모델 데이터를 표시합니다.
* **C(컨트롤러)** 는 브라우저 요청을 처리하는 클래스를 포함합니다. 모델 데이터를 검색하고 응답을 반환하는 뷰 템플릿을 호출합니다. MVC 앱에서 뷰는 정보만 표시합니다. 즉 컨트롤러가 사용자 입력 및 상호 작용을 처리하고 응답합니다.

MVC 패턴을 통해 기존 모놀리식 응용 프로그램보다 테스트 및 업데이트가 용이한 앱을 만들 수 있습니다.

## <a name="tour-your-solution"></a>솔루션 둘러보기

 1. 프로젝트 템플릿은 **MyCoreApp**이라는 단일 ASP.NET Core 프로젝트와 솔루션을 만듭니다. 프로젝트 노드를 확장하면 그 안의 콘텐츠가 표시됩니다.

    ![Visual Studio의 ASP.NET 솔루션 탐색기](../ide/media/csharp-aspnet-solution-explorer-mycoreapp-mvc.png)

 1. **컨트롤러** 폴더에서 *HomeController.cs* 파일을 엽니다.

     ![Visual Studio 솔루션 탐색기의 HomeController.cs 파일](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

 1. *HomeController.cs* 파일을 봅니다.

     ![Visual Studio 코드 창의 HomeController.cs](../ide/media/csharp-aspnet-home-controller-code.png)

 1. 이 프로젝트에는 각 컨트롤러에 매핑되는 하위 폴더를 포함하는 **Views** 폴더도 있습니다. 예를 들어 */Home/About* 경로에 대한 뷰 CSHTML 파일(HTML 확장)은 *Views/Home/About.cshtml*에 있습니다. 해당 파일을 엽니다.

     ![Visual Studio 솔루션 탐색기의 About.cshtml 파일](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

    이 CSHTML 파일은 표준 태그와 인라인 C# 조합을 기준으로 HTML을 렌더링하기 위해 Razor 구문을 사용합니다.

     ![Visual Studio 코드 창의 About.cshtml](../ide/media/csharp-aspnet-about-cshtml-code.png)

    >[!NOTE]
    > Razor에 대한 자세한 내용은 [Razor 구문을 사용하여 C# 및 ASP.NET 시작](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) 페이지를 참조하세요.

 1. 프로젝트에는 웹 사이트의 루트인 **wwwroot** 폴더도 포함됩니다. 내용을 보려면 폴더를 확장합니다.

     ![Visual Studio 솔루션 탐색기의 wwwroot 폴더](../ide/media/csharp-aspnet-solution-wwwroot.png)

    원하는 경로에 직접 &mdash;CSS, 이미지 및 JavaScript 라이브러리와 같은&mdash; 정적 사이트 콘텐츠를 배치할 수 있습니다.

 1. 런타임 시 프로젝트, 해당 패키지 및 앱을 관리하는 여러 구성 파일이 있습니다. 예를 들어 기본 응용 프로그램 [구성](/aspnet/core/fundamentals/configuration)은 *appsettings.json*에 저장됩니다. 하지만 *appsettings.Development.json*을 사용하여 이러한 설정을 재정의할 수 있습니다. **appsettings.json** 파일을 확장하여 **appsettings.Development.json** 파일을 봅니다.

     ![Visual Studio 솔루션 탐색기의 구성 파일](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-debug-and-make-changes"></a>실행, 디버그 및 변경

1. IDE에서 **IIS Express** 단추를 선택하여 디버그 모드에서 앱을 빌드 및 실행합니다. 또는 **F5**를 누르거나 메뉴 모음에서 **디버그 > 디버깅 시작**을 선택합니다.

     ![Visual Studio에서 IIS Express 단추 선택](../ide/media/csharp-aspnet-iis-express-button.png)

     > [!NOTE]
     > **'IIS Express' 웹 서버에 연결할 수 없습니다**라는 오류 메시지가 발생하면 Visual Studio를 닫은 후 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 **관리자 권한으로 실행** 옵션을 사용하여 엽니다. 그런 다음 응용 프로그램을 다시 실행합니다.

1. Visual Studio가 브라우저 창을 시작합니다. **About**을 선택합니다.

   ![앱의 브라우저 창에서 About 선택](../ide/media/csharp-aspnet-browser-page.png)

   무엇보다 브라우저의 **About** 페이지는 *HomeController.cs* 파일에서 설정된 텍스트를 렌더링합니다.

   ![About 페이지에서 텍스트 보기](../ide/media/csharp-aspnet-browser-page-about.png)

1. 브라우저 창을 열어둔 상태에서 Visual Studio로 돌아갑니다. 아직 열려 있지 않으면 *Controllers/HomeController.cs*를 엽니다.

   ![Visual Studio 솔루션 탐색기에서 HomeController.cs 파일 열기](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

1. **About** 메서드의 첫 줄에 중단점을 설정합니다. 이를 위해 여백을 클릭하거나 줄에 커서를 두고 **F9**를 누릅니다.

   이 줄은 *Views/Home/About.cshtml*의 CSHTML 페이지에서 렌더링되는 **ViewData** 컬렉션에 일부 데이터를 설정합니다.

   ![About.cshtml에서 About 메서드의 첫 줄에 중단점을 설정합니다.  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

1. 브라우저로 돌아가 **About** 페이지를 새로 고칩니다. 이렇게 하면 Visual Studio에서 중단점이 트리거됩니다.

1. Visual Studio에서 **ViewData** 멤버 위에 마우스를 가져가 데이터를 확인합니다.

   ![자세한 정보를 보기 위해 About 메서드의 ViewData 멤버 보기](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

1. 중단점을 추가하는 데 사용한 것과 같은 방법으로 응용 프로그램 중단점을 제거합니다.

1. *Views/Home/About.cshtml*을 엽니다.

   ![솔루션 탐색기에서 About.cshtml 선택](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

1. **"additional"** 텍스트를 **"changed"** 으로 변경하여 파일을 저장합니다.

   !["additional" 텍스트를 "changed"로 표시되게 변경](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

1. 브라우저 창으로 돌아가 업데이트된 텍스트를 확인합니다. 변경한 텍스트가 표시되지 않으면 브라우저를 새로 고칩니다.

    ![브라우저 창을 새로 고쳐 변경된 텍스트 확인](../ide/media/csharp-aspnet-browser-page-about-changed.png)

1. 도구 모음에서 **디버깅 중지** 단추를 선택하여 디버깅을 중지합니다. 또는 **Shift**+**F5**를 누르거나 메뉴 모음에서 **디버그** > **디버깅 중지**를 선택합니다.

   ![도구 모음에서 디버깅 중지 단추 선택](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="quick-answers-faq"></a>빠른 답변 FAQ

몇 가지 주요 개념을 강조 표시하는 빠른 FAQ는 다음과 같습니다.

### <a name="what-is-c"></a>C#이란?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework)은 강력하면서도 쉽게 배울 수 있게 설계된 형식이 안전한 개체 지향 프로그래밍 언어입니다.

### <a name="what-is-aspnet-core"></a>ASP.NET Core란? 

ASP.NET Core는 웹앱 및 서비스처럼 인터넷으로 연결된 응용 프로그램을 빌드하기 위한 오픈 소스의 플랫폼 간 프레임워크입니다. ASP.NET Core 앱은 .NET Framework 또는.NET Core에서 실행할 수 있습니다. Windows, Mac 및 Linux에서 ASP.NET Core 앱을 플랫폼 간에 개발하여 실행할 수 있습니다. ASP.NET Core는 [GitHub](https://github.com/aspnet/home)에서 오픈 소스로 제공됩니다.

### <a name="what-is-visual-studio"></a>Visual Studio란?

Visual Studio는 개발자를 위한 통합 개발 생산성 도구입니다. 프로그램과 응용 프로그램을 만드는 데 사용할 수 있는 프로그램으로 생각하면 됩니다.

## <a name="next-steps"></a>다음 단계

축하합니다. 이 자습서를 마쳤습니다. C#, ASP.NET Core 및 Visual Studio IDE를 이해하는 데 도움이 되었기를 바랍니다. C# 및 ASP.NET을 사용하여 웹앱 또는 웹 사이트를 만드는 방법에 대한 자세한 내용은 다음 자습서를 계속 진행합니다.

> [!div class="nextstepaction"]
> [ASP.NET Core를 사용하여 MVC 웹앱 만들기](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x)
>
> [!div class="nextstepaction"]
> [ASP.NET Core를 사용하여 Razor 페이지 웹앱 만들기](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Visual Studio를 사용하여 Azure App Service에 웹앱 게시](..//deployment/quickstart-deploy-to-azure.md)