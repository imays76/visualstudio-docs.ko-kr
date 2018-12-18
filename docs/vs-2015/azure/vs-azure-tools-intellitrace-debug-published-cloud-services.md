---
title: 게시 된 디버깅 Azure 클라우드 서비스 Visual Studio 및 IntelliTrace를 사용 하 여 | Microsoft Docs
description: Visual Studio 및 IntelliTrace를 사용 하 여 클라우드 서비스를 디버그 하는 방법 알아보기
author: mikejo5000
manager: douge
ms.assetid: 5e6662fc-b917-43ea-bf2b-4f2fc3d213dc
ms.topic: conceptual
ms.custom: vs-azure
ms.workload: azure-vs
ms.date: 03/21/2017
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 865642bb7c8e41f81ff4b44ce628082e19b63a56
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002948"
---
# <a name="debugging-a-published-azure-cloud-service-with-visual-studio-and-intellitrace"></a>Visual Studio 및 IntelliTrace를 사용하여 게시된 Azure 클라우드 서비스 디버그
IntelliTrace를 사용 하 여 Azure에서 실행 될 때 역할 인스턴스에 대 한 포괄적인 디버깅 정보를 기록할 수 있습니다. 문제의 원인을 확인 하는 경우에 Azure에서 실행 되는 것 처럼 Visual Studio에서 코드를 단계별로 IntelliTrace 로그를 사용할 수 있습니다. 실제로 IntelliTrace에서 기록 키 코드 실행 및 환경 데이터 Azure 응용 프로그램은 Azure에서 클라우드 서비스로 실행 되 고 Visual Studio에서 기록 된 데이터를 재생할 수 있습니다. 

Visual Studio enterprise를 설치한 경우 IntelliTrace 및 Azure 응용 프로그램 대상.NET Framework 4 또는 이상 버전을 사용할 수 있습니다. IntelliTrace는 Azure 역할에 대 한 정보를 수집합니다. 이러한 역할에 대 한 가상 머신은 항상 64 비트 운영 체제를 실행 합니다.

사용할 수 있습니다 [원격 디버깅](http://go.microsoft.com/fwlink/p/?LinkId=623041) Azure에서 실행 중인 클라우드 서비스에 직접 연결 합니다.

> [!IMPORTANT]
> IntelliTrace는 디버그 시나리오 전용 이며 프로덕션 배포용 쓰일 수 없습니다 합니다.
> 

## <a name="configure-an-azure-application-for-intellitrace"></a>IntelliTrace에 대 한 Azure 응용 프로그램을 구성 합니다.
Azure 응용 프로그램에 대 한 IntelliTrace를 사용 하도록 설정 해야 만들고 Visual Studio Azure 프로젝트에서 응용 프로그램을 게시 합니다. Azure에 게시 하기 전에 Azure 응용 프로그램에 대 한 IntelliTrace를 구성 해야 합니다. IntelliTrace를 구성 하지 않고 응용 프로그램을 게시 하는 경우 프로젝트를 다시 게시 해야 합니다. 자세한 내용은 [Visual Studio를 사용 하 여 프로젝트에 서비스를 Azure 클라우드에 게시](http://go.microsoft.com/fwlink/p/?LinkId=623012)합니다.

1. Azure 응용 프로그램을 배포할 준비가 되었을 때 프로젝트의 빌드 대상이 설정 되어 있는지 확인 하십시오 **디버그**합니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭, 상황에 맞는 메뉴에서 선택 **게시**합니다.
   
1. 에 **Azure 응용 프로그램 게시** 대화 상자, Azure 구독을 선택 하 고 선택 **다음**합니다.

1. 에 **설정을** 페이지에서 합니다 **고급 설정** 탭 합니다.

1. 설정 된 **IntelliTrace 사용** 클라우드에 게시 될 때 응용 프로그램에 대 한 IntelliTrace 로그를 수집 하는 옵션입니다.
   
1. 기본 IntelliTrace 구성을 사용자 지정 하려면 선택 **설정을** 옆에 **IntelliTrace 사용**합니다.

    ![IntelliTrace 설정 링크](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/intellitrace-settings-link.png)
   
1. 에 **IntelliTrace 설정** 대화 상자에서 이벤트 로그, 호출 정보를 수집할지 여부, 로그, 모듈 및 수집 하는 프로세스 및 기록에 할당할 공간의 양을를 지정할 수 있습니다. IntelliTrace에 대 한 자세한 내용은 참조 하세요. [IntelliTrace로 디버깅](http://go.microsoft.com/fwlink/?LinkId=214468)합니다.
   
    ![IntelliTrace 설정](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/IC519063.png)

IntelliTrace 로그는 순환 로그 파일 (기본 크기는 250MB는) IntelliTrace 설정에 지정 된 최대 크기입니다. IntelliTrace 로그는 가상 머신의 파일 시스템의 파일로 수집 됩니다. 로그를 요청 하는 경우 해당 시점에 스냅숏은 가져오고 로컬 컴퓨터에 다운로드 합니다.

Azure 클라우드 서비스를 Azure에 게시 된 후의 Azure 노드에서 IntelliTrace가 활성화 되었는지를 확인할 수 있습니다 **서버 탐색기**다음 그림에 나와 있는 것 처럼:

![서버 탐색기-IntelliTrace 사용](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/IC744134.png)

## <a name="download-intellitrace-logs-for-a-role-instance"></a>역할 인스턴스에 대 한 IntelliTrace 로그 다운로드
Visual Studio를 사용 하 여 이러한 단계를 수행 하 여 역할 인스턴스에 대 한 IntelliTrace 로그를 다운로드할 수 있습니다.

1. **서버 탐색기**를 확장 합니다 **Cloud Services** 노드를 역할 인스턴스에 다운로드 하려는 해당 로그를 찾습니다. 

1. 역할 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 s 상황에 맞는 메뉴에서 선택 **IntelliTrace 로그 보기**합니다. 

    ![IntelliTrace 로그 보기 메뉴 옵션](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/view-intellitrace-logs.png)

1. IntelliTrace 로그 파일 디렉터리에 로컬 컴퓨터에 다운로드 됩니다. IntelliTrace 요청 될 때마다 로그, 새 스냅숏이 생성 됩니다. 로그를 다운로드 하는 동안 Visual Studio에서 작업의 진행률을 표시 합니다 **Azure 활동 로그** 창입니다. 다음 그림에 표시 된 것과 같이 자세한 내용을 보려면 작업에 대 한 품목을 확장할 수 있습니다.

![VST_IntelliTraceDownloadProgress](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/IC745551.png)

IntelliTrace 로그를 다운로드 하는 동안 Visual Studio에서 작업을 계속 수 있습니다. 로그 다운로드 완료 되 면 Visual Studio에서 열립니다.

> [!NOTE]
> IntelliTrace 로그는 프레임 워크를 생성 하 고 나중에 처리 하는 예외를 포함할 수 있습니다. 내부 프레임 워크 코드는 안전 하 게 무시할 수 있도록 역할 시작의 일반적인 한 부분으로 이러한 예외를 생성 합니다.
> 
> 

## <a name="next-steps"></a>다음 단계
- [Azure cloud services 디버깅 옵션](vs-azure-tools-debugging-cloud-services-overview.md)
- [Visual Studio를 사용 하 여 Azure 클라우드 서비스 게시](vs-azure-tools-publishing-a-cloud-service.md)