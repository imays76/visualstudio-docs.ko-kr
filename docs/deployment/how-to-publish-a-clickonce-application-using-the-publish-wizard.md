---
title: '방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램 게시 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- deploying applications [ClickOnce], Publish wizard
- Windows applications, ClickOnce deployments
- publishing, ClickOnce
ms.assetid: 2e4aa67c-4445-4f7b-9e03-9acb95829127
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2943f2a9b0e5d23d40b05a481e45095ad52fc8a8
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39078367"
---
# <a name="how-to-publish-a-clickonce-application-using-the-publish-wizard"></a>방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램 게시
ClickOnce 응용 프로그램을 사용자에게 제공하려면 파일 공유나 경로, FTP 서버 또는 이동식 미디어에 해당 응용 프로그램을 게시해야 합니다. 게시 마법사를 사용 하 여 응용 프로그램을 게시할 수 있습니다. 게시와 관련 된 추가 속성에서 사용할 수는 **게시** 페이지의 **프로젝트 디자이너**합니다. 자세한 내용은 [게시 ClickOnce 응용 프로그램](../deployment/publishing-clickonce-applications.md)합니다.  
  
 게시 마법사를 실행하기 전에 게시 속성을 적절하게 설정해야 합니다. 예를 들어, ClickOnce 응용 프로그램에 서명 하는 키를 지정 하려는 경우 할 수 있는 등의 **서명** 페이지의 **프로젝트 디자이너**합니다. 자세한 내용은 [ClickOnce 보안 응용 프로그램](../deployment/securing-clickonce-applications.md)합니다.  
  
> [!NOTE]
>  응용 프로그램의 이전 버전 이라는 폴더에 이동 ClickOnce를 사용 하 여 응용 프로그램의 둘 이상의 버전을 설치할 때 *보관*를 지정 하는 게시 위치에 있습니다. 이러한 방식으로 이전 버전이 보관되므로 설치 디렉터리에 이전 버전의 폴더가 남지 않습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 실제 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-publish-to-a-file-share-or-path"></a>파일 공유나 경로에 게시하려면  
  
1.  **솔루션 탐색기**, 응용 프로그램 프로젝트를 선택 합니다.  
  
2.  에 **빌드할** 메뉴에서 클릭 **게시** *Projectname*합니다.  
  
     게시 마법사가 나타납니다.  
  
3.  에 **수행 하려는 응용 프로그램을 게시?** 페이지에서 올바른 FTP 서버 주소 또는 아래 형식 중 하나를 사용 하 여 올바른 파일 경로 입력 하 고 클릭 **다음**합니다.  
  
4.  에 **응용 프로그램 설치 방법?** 페이지, 응용 프로그램을 설치 하려면 사용자가 이동할 위치를 선택:  
  
    -   사용자가 웹 사이트에서 설치를 클릭 **웹 사이트에서** 하 고 이전 단계에서 입력 된 파일 경로를 해당 하는 URL을 입력 합니다. **다음**을 클릭합니다. 이 옵션은 일반적으로 FTP 주소를 게시 위치로 지정하는 경우에 사용됩니다. FTP에서 직접 다운로드할 수는 없습니다. 따라서 여기에 URL을 입력해야 합니다.  
  
    -   사용자가 응용 프로그램 파일 공유에서 직접을 설치 하는 경우 클릭 **UNC 경로 또는 파일 공유**를 클릭 하 고 **다음**합니다. (이 폼의 위치를 쉽게 게시할 *c:\deploy\myapp* 하거나  *\\\server\myapp*.)  
  
    -   사용자가 이동식 미디어에서 설치를 클릭 **CD-ROM 또는 DVD-ROM**를 클릭 하 고 **다음**합니다.  
  
5.  에 **응용 프로그램을 오프 라인으로 사용할 수?** 페이지에서 적절 한 옵션을 클릭 합니다.  
  
    -   응용 프로그램을 실행할 수 있도록 하려는 경우 사용자는 연결이 끊어진 경우 네트워크에서 클릭 **예,이 응용 프로그램은 온라인 또는 오프 라인으로 사용할 수**입니다. 에 대 한 바로 가기 합니다 **시작** 응용 프로그램에 대 한 메뉴 만들어집니다.  
  
    -   게시 위치에서 직접 응용 프로그램을 실행 하려면 클릭 **아니요,이 응용 프로그램은 온라인 으로만 사용할 수 있는**합니다. 에 대 한 바로 가기 합니다 **시작** 메뉴 생성 되지 것입니다.  
  
     **다음** 을 클릭하여 계속합니다.  
  
6.  클릭 **완료** 응용 프로그램을 게시 합니다.  
  
     게시 상태가 상태 알림 영역에 표시됩니다.  
  
### <a name="to-publish-to-a-cd-rom-or-dvd-rom"></a>CD-ROM 또는 DVD-ROM에 게시하려면  
  
1.  **솔루션 탐색기**응용 프로그램 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.  
  
     **프로젝트 디자이너**가 표시됩니다.  
  
2.  클릭는 **게시** 탭을 열고를 **게시** 페이지를 **프로젝트 디자이너**, 클릭 하 고를 **게시 마법사** 단추.  
  
     게시 마법사가 나타납니다.  
  
3.  에 **수행 하려는 응용 프로그램을 게시?** 페이지에서 입력 파일 경로나 FTP는 응용 프로그램을 게시할 위치, 예를 들어 *d:\deploy*합니다. 누른 **다음** 계속 합니다.  
  
4.  에 **응용 프로그램 설치 방법?** 페이지에서 클릭 합니다는 **CD-ROM 또는 DVD-ROM**를 클릭 하 고 **다음**합니다.  
  
    > [!NOTE]
    >  자동으로 실행 되도록 설치 하려는 경우 CD-ROM를 삽입할 때 드라이브에 열려를 **게시** 페이지에 **프로젝트 디자이너** 클릭 합니다 **옵션** 단추를 선택한 다음 합니다 **게시 옵션** 마법사 **CD를 삽입 하면 CD 설치에서 설치 프로그램을 자동으로 시작**합니다.  
  
5.  CD-ROM으로 응용 프로그램을 배포하는 경우 웹 사이트에서 업데이트를 제공할 수 있습니다. 에 **응용 프로그램이 업데이트를 확인할 위치?** 페이지에서 업데이트 옵션을 선택 합니다.  
  
    -   응용 프로그램 업데이트를 확인 하면, 클릭 **응용 프로그램은 다음 위치에서 업데이트가 있는지 확인** 업데이트가 게시 될 위치를 입력 합니다. 이 위치는 파일 위치, 웹 사이트 또는 FTP 서버일 수 있습니다.  
  
    -   응용 프로그램 업데이트 확인 하지 것입니다, 클릭 **응용 프로그램 업데이트 확인 하지 것입니다**합니다.  
  
     **다음** 을 클릭하여 계속합니다.  
  
6.  클릭 **완료** 응용 프로그램을 게시 합니다.  
  
     게시 상태가 상태 알림 영역에 표시됩니다.  
  
    > [!NOTE]
    >  게시가 완료되면 CD 재작성기 또는 DVD 재작성기를 사용하여 3단계에서 지정한 위치에서 CD-ROM 또는 DVD-ROM 미디어로 파일을 복사합니다.  
  
## <a name="see-also"></a>참고자료  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)