---
title: 시작 페이지 사용자 지정 만들기 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d67e0c53-9f5a-45fb-a929-b9d2125c3c82
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 52050641ee9d2d522ff07dd5eaed72ecbec2b09e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53941442"
---
# <a name="creating-a-custom-start-page"></a>사용자 지정 시작 페이지 만들기
이 문서의 단계를 수행 하 여 사용자 지정 시작 페이지를 만들 수 있습니다.  
  
## <a name="create-a-blank-start-page"></a>빈 시작 페이지 만들기  
 먼저 만들어 빈 시작 페이지를 확인 한 *.xaml* 파일을 Visual Studio에서 인식 되는 태그 구조를 갖습니다. 태그 및 코드 숨김 모양과 기능을 생성 하기 위해 추가 합니다.  
  
### <a name="to-create-a-blank-start-page"></a>빈 시작 페이지를 만들려면  
  
1.  형식의 새 프로젝트를 만듭니다 **WPF 응용 프로그램** (**Visual C#** > **Windows Desktop**).  
  
2.  `Microsoft.VisualStudio.Shell.14.0`에 대한 참조를 추가합니다.  
  
3.  XML 편집기에서 XAML 파일을 열고 변경 최상위 \<창 > 요소는 \<UserControl > 네임 스페이스 선언 중 하나를 제거 하지 않고 요소입니다.  
  
4.  제거 된 `x:Class` 최상위 요소에서 선언 합니다. 이렇게 하면 XAML 콘텐츠에 시작 페이지를 호스팅하는 Visual Studio 도구 창 호환입니다.  
  
5.  최상위 다음 네임 스페이스 선언을 추가 \<UserControl > 요소입니다.  
  
    ```vb  
    xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
    xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
    ```  
  
     이러한 네임 스페이스를 통해 Visual Studio 명령, 컨트롤 및 UI 설정에 액세스할 수 있습니다. 자세한 내용은 [시작 페이지를 Visual Studio 추가 명령을](../extensibility/adding-visual-studio-commands-to-a-start-page.md)합니다.  
  
     다음 예제에서는 태그를 *.xaml* 빈 시작 페이지에 대 한 파일입니다. 사용자 지정 내용을 내부로 이동 되도록 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
    ```vb  
    <UserControl  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        xmlns:MyNamespace="clr-namespace:ManualStartPage;assembly=ManualStartPage"  
        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
                xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
        xmlns:local="clr-namespace:StartPageHost"  
        mc:Ignorable="d"  
         Height="350" Width="525">  
        <Grid>  
        <!--Add content here.-->  
        </Grid>  
    </UserControl>  
    ```  
  
6.  빈 컨트롤을 추가할 \<UserControl > 사용자 지정 시작 페이지를 작성 하는 요소입니다. Visual Studio에 관련 된 기능을 추가 하는 방법에 대 한 정보를 참조 하세요 [시작 페이지를 Visual Studio 추가 명령을](../extensibility/adding-visual-studio-commands-to-a-start-page.md)합니다.  
  
## <a name="test-and-apply-the-custom-start-page"></a>테스트 및 사용자 지정 시작 페이지를 적용 합니다.  
 Visual Studio 충돌 하지 않는 것을 확인 하기 전에 사용자 지정 시작 페이지를 실행 하려면 Visual Studio의 기본 인스턴스를 설정 하지 마십시오. 대신, 실험적 인스턴스에서 테스트 합니다.  
  
### <a name="to-test-a-manually-created-custom-start-page"></a>수동으로 만든 사용자 지정 시작 페이지를 테스트 하려면  
  
1.  XAML 파일에 및 지원 텍스트 파일 또는 태그 파일에 복사 합니다 *%USERPROFILE%\My Documents\Visual Studio 2015\StartPages\\*  폴더입니다.  
  
2.  시작 페이지에서 모든 컨트롤 또는 Visual Studio가 설치 되지 않은 어셈블리의 형식을 참조 하는 경우 어셈블리를 복사한 다음에 붙여 넣습니다 *{Visual Studio 설치 폴더} \Common7\IDE\PrivateAssemblies\\* .  
  
3.  Visual Studio 명령 프롬프트에서 입력 **devenv /rootsuffix Exp** Visual Studio의 실험적 인스턴스를 엽니다.  
  
4.  실험적 인스턴스를 이동 합니다 **도구가** > **옵션** > **환경** > **시작** 페이지에서 XAML 파일을 선택 하 고는 **시작 페이지 사용자 지정** 드롭다운 합니다.  
  
5.  **보기** 메뉴에서 **시작 페이지**를 클릭합니다.  
  
     사용자 지정 시작 페이지에 표시 되어야 합니다. 파일을 변경 하려는 경우 실험적 인스턴스, 변경, 복사 및 변경 된 파일을 붙여넣을 닫은 다음 변경 내용을 보려면 실험적 인스턴스를 다시 엽니다.  
  
### <a name="to-apply-the-custom-start-page-in-the-primary-instance-of-visual-studio"></a>Visual Studio의 기본 인스턴스에서 사용자 지정 시작 페이지에 적용  
  
-   시작 페이지를 테스트 하 고 안정적인 수를 사용 하 여 합니다 **시작 페이지 사용자 지정** 옵션을 **옵션** Visual Studio의 기본 인스턴스에서 시작 페이지로 선택 대화 상자  
  
## <a name="see-also"></a>참고 항목  
 [연습: 시작 페이지 사용자 지정 XAML 추가](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)   
 [시작 페이지에 사용자 정의 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)   
 [시작 페이지에 Visual Studio 명령 추가](../extensibility/adding-visual-studio-commands-to-a-start-page.md)   
 [연습: 시작 페이지에서 사용자 설정 저장](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md)   
 [사용자 지정 시작 페이지를 배포 합니다.](../extensibility/deploying-custom-start-pages.md)