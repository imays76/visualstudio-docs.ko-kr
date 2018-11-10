---
title: Visual Studio에서 연결 된 서비스를 사용 하 여 Azure Storage 추가 | Microsoft Docs
description: Visual Studio 연결 된 서비스 추가 대화 상자를 사용 하 여 앱에 Azure Storage 추가
author: ghogen
manager: douge
assetId: 521ec044-ad4b-4828-8864-01decde2e758
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/26/2017
ms.author: ghogen
ms.openlocfilehash: 63b796d9c514602a40f15b5725c07b1b89787df1
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002338"
---
# <a name="adding-azure-storage-by-using-visual-studio-connected-services"></a>Visual Studio 연결 서비스를 사용 하 여 Azure storage 추가
Visual Studio를 사용 하 여 여 연결할 수 있습니다 다음 중 하나를 Azure Storage를 사용 하 여 **연결 된 서비스 추가** 대화 상자:

- C#클라우드 서비스
- .NET 백 엔드 모바일 서비스
- ASP.NET 웹 사이트 또는 서비스
- ASP.NET Core 서비스
- Azure WebJob 서비스 

연결 된 서비스 기능은 프로젝트에 모든 필요한 참조와 연결 코드를 추가 하 고 구성 파일을 적절 하 게 수정 합니다. 

작업이 완료 되 면 합니다 **연결 된 서비스 추가** 대화 상자에서 자동으로 큐, blob storage를 사용 하 여 작업을 시작 하는 데 필요한 단계를 자세히 설명 하는 설명서를 표시 하 고 테이블입니다.

## <a name="connect-to-azure-storage-using-the-connected-services-dialog"></a>연결 된 서비스 대화 상자를 사용 하 여 Azure Storage에 연결
1. Visual Studio에서 프로젝트를 엽니다.

1. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **연결 된 서비스** 노드를 선택한 상황에 맞는 메뉴에서 **연결 된 서비스 추가**합니다.
   
    ![추가 Azure 서비스를 연결 합니다.](./media/vs-azure-tools-connected-services-storage/IC796702.png)

1. 에 **연결 된 서비스** 페이지에서 **Azure Storage를 사용 하 여 클라우드 Storage**합니다.
   
    ![Azure Storage 추가](./media/vs-azure-tools-connected-services-storage/add-azure-storage.png)

1. 에 **Azure Storage** 대화 상자, 기존 저장소 계정 선택 하 고 선택 **추가**합니다.
   
    저장소 계정 만들기 해야 할 경우 다음 단계로 이동 합니다. 그렇지 않으면 6 단계로 건너뜁니다.
    
    ![프로젝트에 기존 저장소 계정 추가](./media/vs-azure-tools-connected-services-storage/select-azure-storage-account.png)

1. 저장소 계정을 만들려면: 
   
   1. 선택 **새 저장소 계정을 만드는** 대화 상자의 맨 아래에 있습니다.

   1. 입력 합니다 **Storage 계정 만들기** 대화 상자에서 선택한 **만들기**합니다.
      
       ![새 Azure storage 계정](./media/vs-azure-tools-connected-services-storage/create-storage-account.png)
      
   1. 경우는 **Azure Storage** 대화 상자가 표시 됩니다, 새 저장소 계정 목록에 나타납니다. 새 저장소 계정 목록에서 선택한 **추가**합니다.

1. 저장소 연결된 서비스 아래에 표시 합니다 **서비스 참조** 프로젝트의 노드.
   
## <a name="how-your-project-is-modified"></a>프로젝트를 수정 하는 방법
대화 상자를 완료 하면 Visual Studio는 참조를 추가 하 고 특정 구성 파일을 수정 합니다. 특정 변경 내용은 프로젝트 형식에 따라 달라 집니다. 

- ASP.NET 프로젝트- [내용 – ASP.NET 프로젝트](http://go.microsoft.com/fwlink/p/?LinkId=513126)
- ASP.NET Core 프로젝트- [내용 – ASP.NET 5 프로젝트](http://go.microsoft.com/fwlink/p/?LinkId=513124) 
- 클라우드 서비스 프로젝트 (웹 역할 및 작업자 역할)- [내용 – 클라우드 서비스 프로젝트](http://go.microsoft.com/fwlink/p/?LinkId=516965)
- WebJob 프로젝트- [내용-WebJob 프로젝트](/azure/visual-studio/vs-storage-webjobs-what-happened)

## <a name="next-steps"></a>다음 단계
- [MSDN 포럼: Azure Storage](https://social.msdn.microsoft.com/forums/azure/home?forum=windowsazuredata)
- [Microsoft Azure Storage 팀 블로그](http://blogs.msdn.com/b/windowsazurestorage/)
- [Azure Storage 설명서](https://docs.microsoft.com/azure/storage/)
