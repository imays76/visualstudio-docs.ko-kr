---
title: Visual Studio 버전에서 나란히 설치 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- side-by-side installations [Visual Studio]
- Help [Visual Studio], installing
- install multiple versions of Visual Studio
ms.assetid: 4d00f240-4910-4699-aaf3-cda6461f0c29
caps.latest.revision: 48
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: ae67e83b2f1444c09129ed5242afac2c3939c954
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556852"
---
# <a name="install-visual-studio-versions-side-by-side"></a>Visual Studio 버전-Side-by-side 설치
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이전 버전이 설치된 컴퓨터에 이 버전의 Visual Studio를 설치할 수 있습니다. 설치 오류가 발생할 경우 문제를 직접 디버그할 수 있도록 [로그 수집 도구](http://go.microsoft.com/fwlink/?LinkId=262077) 를 사용하여 오류에 대한 정보를 수집할 수 있습니다.  
  
> [!NOTE]
>  설치 하는 것이 좋습니다 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 버전 출시 된 순서입니다. 예를 들어 Visual Studio 2015를 설치하기 전에 Visual Studio 2013을 설치합니다.  
  
 여러 버전을 함께 설치하기 전에 다음과 같은 조건을 검토해야 합니다.  
  
-   만든 솔루션을 열려면 Visual Studio 2015를 사용 하는 경우 [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)], 나중에 열려면 하 고 Visual Studio 2015 특정 기능을 구현 하지 않은 이전 버전에서 다시 솔루션을 수정할 수 있습니다.  
  
-   만든 솔루션을 열려면 Visual Studio 2015를 사용 하려는 경우 [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)] 이전 버전을 프로젝트와 Visual Studio 2015와 호환 되도록 파일을 수정 해야 할 수 있습니다. 자세한 내용은 참조는 [포트, 마이그레이션 및 Visual Studio 프로젝트 업그레이드](../misc/port-migrate-and-upgrade-visual-studio-projects-in-visual-studio-15-rc.md) 페이지입니다.  
  
-   둘 이상의 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 버전이 설치된 컴퓨터에서 한 버전을 제거할 경우 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]의 파일 연결이 모든 버전에 대해 제거됩니다. 사용 하 여이 파일 연결을 다시 매핑할 수 있습니다는 **파일 연결 복원** 단추를 **환경**를 **일반** 페이지는 [옵션](../ide/reference/general-environment-options-dialog-box.md) 대화 상자.  
  
-   모든 확장이 호환되는 것은 아니므로 Visual Studio에서는 확장을 자동으로 업그레이드하지 않습니다. [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkId=178891) 또는 소프트웨어 게시자에서 확장을 다시 설치해야 합니다.  
  
## <a name="net-framework-versions-and-side-by-side-installations"></a>.NET Framework 버전 및 Side-by-Side 설치  
  
-   Visual Basic, Visual C# 및 Visual F# 프로젝트에는 **프로젝트 디자이너** 의 **대상 프레임워크** 옵션을 사용하여 프로젝트에 사용할 .NET Framework 버전을 지정합니다. C++ 프로젝트의 경우 .vcxproj 파일을 수정하여 수동으로 대상 프레임워크를 변경할 수 있습니다. 자세한 내용은 [버전 호환성](http://msdn.microsoft.com/library/2f25e522-456a-48c3-8a53-e5f39275649f)합니다.  
  
     프로젝트를 만들 때 **새 프로젝트** 대화 상자의 **.NET Framework** 목록에서 프로젝트 대상으로 사용할 .NET Framework 버전을 지정할 수 있습니다.  
  
     언어별 정보는 다음 테이블에서 해당 항목을 참조하세요.  
  
    |언어|항목|  
    |--------------|-----------|  
    |[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]|[프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)|  
    |Visual C#|[프로젝트 디자이너, 응용 프로그램 페이지(C#)](../ide/reference/application-page-project-designer-csharp.md)|  
    |Visual F#|[프로젝트 구성](http://msdn.microsoft.com/library/a1489abb-6294-4f8f-b71f-2cb126393526)|  
    |C++|[방법: 대상 프레임워크 및 플랫폼 도구 집합 수정](http://msdn.microsoft.com/library/031b1d54-e6e1-4da7-9868-3e75a87d9ffe)|  
    |[!INCLUDE[jsprjscript](../includes/jsprjscript-md.md)]|[이전 버전의 공용 언어 런타임에서 JScript 응용 프로그램 실행](http://msdn.microsoft.com/en-us/bbea51b5-ac03-4e6c-b9a6-f487ef63eda5)|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio를 설치](../install/install-visual-studio-2015.md) [포팅, 마이그레이션 및 Visual Studio 프로젝트 업그레이드](../misc/port-migrate-and-upgrade-visual-studio-projects-in-visual-studio-15-rc.md)   
 [격리 된 응용 프로그램 및 side-by-side-어셈블리 C/c + + 빌드](http://msdn.microsoft.com/library/9465904e-76f7-48bd-bb3f-c55d8f1699b6)   
 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)