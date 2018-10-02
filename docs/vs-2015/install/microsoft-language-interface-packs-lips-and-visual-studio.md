---
title: Microsoft 언어 인터페이스 팩 (Lip) 및 Visual Studio | Microsoft Docs
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
- text [Visual Studio], multiple languages
- Multilingual User Interface [Visual Studio]
- language switching [Visual Studio]
- MUI [Visual Studio]
- multiple language support [Visual Studio SDK]
- Windows Multilingual User Interface
- UI text language [Visual Studio]
- languages, multiple language support
ms.assetid: dc86304b-65b7-47e6-9314-1dfd02ecfa65
caps.latest.revision: 28
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 297bc0f1c2a052ffb71b1b7573b292c20d0ea4ea
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550252"
---
# <a name="microsoft-language-interface-packs-lips-and-visual-studio"></a>Microsoft LIP(언어 인터페이스 팩) 및 Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows LIP(언어 인터페이스 팩)를 사용하면 Windows 언어 버전을 설치한 다음 다양한 사용자 인터페이스 언어 팩을 설치할 수 있습니다. 사용자 인터페이스 언어 팩은 운영 체제에 대한 지역화된 UI(사용자 인터페이스)를 제공합니다. 예를 들어 영어 버전의 Windows에 한국어 언어 인터페이스 팩을 설치한 다음 Windows UI 언어를 한국어와 영어 간에 전환할 수 있습니다. LIP를 통해 한 컴퓨터에서 여러 언어 버전의 Windows를 사용할 수도 있습니다.  
  
 LIP 및 여러 언어 버전의 Visual Studio가 설치된 컴퓨터에서 Windows 표시 언어 설정을 변경하면 일치하는 언어 팩이 설치된 경우 Windows 및 Visual Studio 둘 다 설정됩니다.  
  
## <a name="limitations-of-multi-language-installations"></a>다중 언어 설치의 제한 사항  
 동일한 컴퓨터에 여러 언어 버전의 Visual Studio를 설치하는 경우 일치하는 버전 간에만 언어를 전환할 수 있습니다. 예를 들어 영어 Express Edition, 독일어 Express Edition 및 Professional Edition이 설치되어 있는 경우 Express Edition에 대한 언어만 전환할 수 있고 Professional Edition에 대한 언어는 전환할 수 없습니다.  
  
 Visual Studio는 통합된 언어 팩을 사용합니다. 이러한 제품의 언어 버전을 두 개 이상 설치하려면 전체 언어 제품을 먼저 설치한 다음 하나 이상의 언어 팩을 설치해야 합니다.  
  
> [!NOTE]
>  Visual Studio는 같은 컴퓨터에서 전체 언어 제품의 다중 언어 버전 설치를 지원하지 않습니다. 하나의 전체 언어 제품을 설치한 후 언어 팩을 사용하여 언어 버전을 추가해야 합니다. 동일한 컴퓨터에 Express Edition의 전체 언어 제품을 여러 개 설치할 수는 있습니다.  
  
### <a name="support-for-code-pages"></a>코드 페이지에 대한 지원  
 텍스트가 현재 코드 페이지에 없는 문자를 포함하는 경우 일부 Visual Studio 도구에서는 텍스트가 올바르게 표시되지 않습니다. 대신, 물음표가 나타나거나 텍스트가 손상됩니다. 다음과 같은 도구 또는 영역이 영향을 받습니다.  
  
-   FTP를 사용하여 배포된 사이트  
  
-   일부 컨트롤에 포함된 비 ASCII 컴퓨터 이름  
  
-   Visual Studio 외부에서 실행되는 명령줄 도구  
  
-   Visual Basic 마이그레이션 마법사  
  
-   ActiveX Control Test Container  
  
-   OLE/COM 개체 뷰어  
  
-   ISAPI 웹 디버그 도구  
  
-   HTML 도움말 콘텐츠가 있는 MFC 응용 프로그램 프로젝트  
  
-   Visual SourceSafe SCCI UI는 호환되지 않는 코드 페이지가 있는 경우 영어로 대체됩니다.  
  
-   Visual SourceSafe는 유니코드 파일 이름을 지원하지 않습니다.  
  
-   최종 사용자 정의 문자(개인 사용 영역)는 토큰/식별자로 사용할 수 없습니다.  
  
-   Windows 코드 페이지가 동아시아 언어로 설정된 경우 일부 Visual Studio 도구에서는 라틴어 확장-B 문자를 표시할 수 없습니다.  
  
-   여러 언어 스크립트의 문자로 구성된 텍스트 실행에서는 일부 문자에 대해 기본 문자 모양이 표시될 수도 있습니다.  
  
-   공용 컨트롤에 복잡한 스크립트 문자열을 복사하여 붙여넣을 경우 문자 모양이 손실될 수 있습니다. 대신, 해당 언어 키보드를 사용하여 텍스트를 입력합니다.  
  
##### <a name="to-correctly-display-characters-that-are-not-included-in-the-current-code-page"></a>현재 코드 페이지에 포함되지 않은 문자를 올바르게 표시하려면  
  
1.  클릭 **시작**, 클릭 **제어판**을 연 다음 **국가 및 언어 옵션** (또는 **지역** 에서 [!INCLUDE[win8](../includes/win8-md.md)]).  
  
    > [!NOTE]
    >  이 단계를 수행하려면 컴퓨터의 관리자여야 합니다.  
  
2.  **고급** 탭을 클릭합니다.  
  
3.  에 **언어를 사용 하려면 유니코드가 아닌 프로그램의 언어 버전과 일치 하도록 선택** 목록에서 현재 사용 중인 언어를 선택 합니다.  
  
4.  **확인**을 클릭합니다.  
  
## <a name="changing-the-language-used-for-the-ui-text-in-visual-studio"></a>Visual Studio에서 UI 텍스트에 사용되는 언어 변경  
 여러 언어 버전을 설치 하는 경우 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 동일한 컴퓨터에 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 기본적으로 UI **Microsoft Windows와 같음**합니다. 이 설정 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 운영 체제의 표시 언어로 지정 된 언어로 UI 텍스트가 표시 됩니다.  
  
> [!NOTE]
>  Visual Studio가 사용 하도록 설정 하는 경우 **Microsoft Windows와 같음**, 및는 일치 하는 Visual Studio 언어 팩이 설치 되지, Visual Studio에서 첫 번째 Visual Studio 설치의 언어를 사용 하는 합니다.  
  
#### <a name="to-set-the-language-that-is-used-for-the-ui-text-in-visual-studio"></a>Visual Studio에서 UI 텍스트에 사용되는 언어를 설정하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  에 **옵션** 대화 상자에서 **환경** 을 클릭 한 다음 **국가별 설정**합니다.  
  
3.  에 **언어** 목록에서 개발 환경에서 UI 텍스트를 표시할 언어를 선택 합니다.  
  
     가 UI 텍스트가 일치 하는 IDE에서에서 설정 하는 운영 체제 표시 언어 선택 **Microsoft Windows와 같음**합니다.  
  
 devenv 명령을 통해 UI에 사용되는 언어를 설정할 수도 있습니다. 자세한 내용은 [/LCID (devenv.exe)](../ide/reference/lcid-devenv-exe.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [옵션 대화 상자, 환경, 국가별 설정](../ide/reference/international-settings-environment-options-dialog-box.md)