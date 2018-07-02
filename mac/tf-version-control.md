---
title: TF 버전 제어
description: Team Foundation 버전 제어를 사용하여 Team Foundation Server 또는 Visual Studio Team Services에 연결.
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 58d0fc5c31b02574661f8b86a4ae8bcaf393be3a
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693775"
---
# <a name="connecting-to-team-foundation-version-control"></a>eam Foundation 버전 제어에 연결 

> [!NOTE]
> **참고**: Team Foundation 버전 제어 지원은 현재 미리 보기 상태이며, 일부 기능은 아직 완전히 작동하지 않습니다. 모든 문제에 대한 피드백을 [개발자 커뮤니티](https://developercommunity.visualstudio.com/spaces/41/index.html)에 올려주시면 감사하겠습니다. 아직 변경의 여지가 많이 있습니다.

VSTS(Visual Studio Team Services) 및 TFS(Team Foundation Server)는 분산형 버전 제어인 Git와 중앙 집중식 버전 제어인 TFVC(Team Foundation Version Control)라는 두 가지 버전 제어 모드를 제공합니다. 이 아티클에서는 Mac용 Visual Studio에서 Team Foundation 버전 제어를 사용하는 방법에 대한 개요와 그 시작점을 제공합니다.

## <a name="requirements"></a>요구 사항

* Mac용 Visual Studio 버전 7.5 이상.
* Visual Studio Team Services 또는 Team Foundation Server 2013 이상
* Team Foundation 버전 제어를 사용하도록 구성된 Visual Studio Team Services 또는 Team Foundation Server의 프로젝트.

## <a name="installation"></a>설치

Mac용 Visual Studio의 메뉴에서 **Visual Studio > 확장...** 을 선택합니다. **갤러리** 탭에서 **버전 제어 > TFS 및 VSTS용 Team Foundation 버전 제어**를 선택하고 **설치...** 을 클릭합니다.

  ![확장 관리자](media/tfvc-install.png) 

표시되는 메시지에 따라 확장을 설치합니다. 설치가 완료되면 IDE를 다시 시작합니다.

## <a name="using-the-add-in"></a>추가 기능 사용

확장이 설치되면 **버전 제어 > TFS/VSTS > Team Foundation 버전 제어에 연결...** 메뉴 항목을 선택합니다. **추가**를 클릭하여 새 계정을 추가합니다. 

![TFVC 서버 추가](media/tfvc-add-remove-server.png)

Visual Studio Team Services 또는 Team Foundation Server를 선택하여 시작:

![TFVC 서버와 연결](media/tfvc-choose-server-type.png)

자격 증명을 입력하고 **로그인**을 클릭합니다. 

![TFVC 서버에 로그인](media/tfvc-login.png)

로그인에 성공하면 액세스할 프로젝트를 선택하고 **확인**을 누릅니다. 

![프로젝트 선택](media/tfvc-choose-projects.png)

**버전 제어 > TFS/VSTS > 소스 제어 탐색기** 메뉴 항목을 선택하여 소스를 탐색할 수 있는 소스 제어 탐색기를 엽니다.

> [!IMPORTANT]
> **알려진 문제**: 이 미리 보기 릴리스에서는 처음으로 소스 제어 탐색기를 열 때 [새 작업 영역을 만들기](#creating-a-new-workspace)를 해야만 합니다.

![소스 탐색기](media/tfvc-source-explorer.png)

소스 코드 탐색기에서 서버의 소스 코드를 찾아보고 다음 작업을 수행할 수 있습니다.

- 작업 영역 관리(만들기, 편집 또는 삭제).
- 프로젝트 구조 사이로 이동.
- 프로젝트 매핑.
- 프로젝트 가져오기.
- 파일 잠금 및 잠금 해제.
- 파일 이름 바꾸기.
- 파일 삭제.
- 새 파일 추가.
- 체크 아웃.
- 체크 인.
- 변경 기록 보기.
- 변경 내용 비교.

## <a name="creating-a-new-workspace"></a>새 작업 영역 만들기

소스 제어 탐색기에서 **작업 영역 관리** 단추를 클릭합니다. 

![작업 영역 관리](media/tfvc-manage-workspaces.png)

**추가** 단추를 클릭하여 새 작업 영역을 만듭니다.

![작업 영역 만들기](media/tfvc-create-workspace.png)

작업 영역의 이름을 지정한 후 **작업 폴더 추가**를 클릭하여 컴퓨터의 로컬 폴더에 프로젝트를 매핑합니다.

완료되면 **확인**을 클릭한 후 작업 영역 관리 대화 상자를 닫습니다. 이제 소스 코드 탐색기를 통해 파일을 가져와 시작할 수 있습니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="problems-using-basic-authentication"></a>기본 인증 사용 문제

서버에서 인증을 수행하는 데 사용할 수 있는 여러 가지 옵션이 있습니다.

- Oauth
- Basic
- Ntlm

기본 인증을 사용하려면 다음 단계에 따라 VSTS에서 **대체 인증 자격 증명**을 활성화해야 합니다.

1. VSTS 계정(https://{youraccount}.visualstudio.com)에 계정 소유자로 로그인합니다.
2. 계정 도구 모음에서 기어 아이콘을 선택하고 **정책**: ![정책 설정 옵션 선택](media/tfvc-auth2.png)을 선택합니다. 
3. 응용 프로그램 연결 설정을 검토합니다. 보안 정책: ![정책 설정 옵션 선택](media/tfvc-auth.png)에 따라 이러한 설정을 변경합니다.  

### <a name="i-do-not-see-anything-in-tfvc"></a>TFVC에 아무것도 표시되지 않음

개발 컴퓨터에서 TFVC(Team Foundation 버전 제어)를 설정하려면 [새 작업 영역 만들기](#creating-a-new-workspace) 섹션에 설명된 대로 작업 영역을 **만들어야** 합니다.

소스 제어 탐색기에서 **작업 영역 관리** 단추를 누릅니다. 팀 프로젝트를 개발 컴퓨터의 폴더에 매핑하는 단계를 수행합니다.

### <a name="i-do-not-see-any--all-of-my-projects"></a>내 프로젝트 중 일부/전부가 표시되지 않음

인증 후 프로젝트 목록을 확인해야 합니다. 기본적으로 TFS 프로젝트만 표시됩니다. 다른 형식의 프로젝트를 보려면 "모든 프로젝트 보기" 상자를 선택합니다.

올바른 권한이 없는 경우 서버에 있는 프로젝트가 표시되지 않습니다.

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>"작업 영역을 만들 수 없습니다. 다시 시도하세요."라는 오류 메시지가 나타납니다.

[새 작업 영역 만들기](#creating-a-new-workspace)를 수행할 때 다음 조건이 충족되었는지 확인해야 합니다.

- 작업 영역 이름에 잘못된 문자를 사용하지 마세요.
- 이름은 64자 미만이어야 합니다.
- 로컬 경로는 다른 작업 영역에서 사용할 수 없습니다.