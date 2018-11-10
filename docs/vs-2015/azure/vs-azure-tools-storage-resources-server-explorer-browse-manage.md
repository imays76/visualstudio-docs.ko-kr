---
title: 검색 하 고 서버 탐색기를 사용 하 여 저장소 리소스 관리 | Microsoft Docs
description: 찾아보기 및 서버 탐색기를 사용 하 여 저장소 리소스 관리
author: ghogen
manager: douge
assetId: 658dc064-4a4e-414b-ae5a-a977a34c930d
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/24/2017
ms.author: ghogen
ms.openlocfilehash: 00229cd88ddcab4d2d59ae40202620c374415e4b
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51003048"
---
# <a name="browse-and-manage-storage-resources-by-using-server-explorer"></a>서버 탐색기를 사용하여 저장소 리소스 찾아보기 및 관리

[!INCLUDE [storage-try-azure-tools](./includes/storage-try-azure-tools.md)]

## <a name="overview"></a>개요

Microsoft Visual Studio 용 Azure 도구를 설치한 경우 보면 blob, 큐 및 테이블 데이터 저장소 계정에서 Azure에 대 한 합니다. Azure **저장소** 서버 탐색기에서 노드 로컬 저장소 에뮬레이터 계정 및 다른 Azure storage 계정에 있는 데이터를 표시 합니다.

Visual Studio에서 메뉴 모음에서 서버 탐색기를 보려면를 선택 **뷰** > **서버 탐색기**합니다. 합니다 **저장소** 노드는 각 Azure 구독 또는 인증서에 연결 하는 아래에 있는 저장소 계정의 모든 보여줍니다. 저장소 계정이 나타나지 않으면 지침에 따라 추가할 수 있습니다 [이 문서의 뒷부분에 나오는](#add-storage-accounts-by-using-server-explorer)합니다.

Azure SDK 2.7부터는 보고 Azure 리소스를 관리 하려면 클라우드 탐색기를도 사용할 수 있습니다. 자세한 내용은 [클라우드 탐색기를 사용 하 여 Azure 관리 리소스](vs-azure-tools-resources-managing-with-cloud-explorer.md)합니다.

## <a name="view-and-manage-storage-resources-in-visual-studio"></a>Visual Studio에서 저장소 리소스 보기 및 관리

서버 탐색기는 저장소 에뮬레이터 계정의 blob, 큐 및 테이블 목록을 자동으로 표시 됩니다. 저장소 에뮬레이터 계정에서 서버 탐색기에 나열 되는 **저장소** 노드를 **개발** 노드.

저장소 에뮬레이터 계정의 리소스를 보려면 확장 합니다 **개발** 노드. 확장 하면 저장소 에뮬레이터가 시작 되지 않은 경우는 **개발** 노드를 자동으로 시작 합니다. 이 프로세스는 몇 초 정도 걸릴 수 있습니다. 저장소 에뮬레이터를 시작 하는 동안 Visual Studio의 다른 영역에서 작업을 계속 수 있습니다.

저장소 계정에 리소스를 보려면 표시 되는 서버 탐색기에서 저장소 계정의 노드를 확장 **Blob**하십시오 **큐**, 및 **테이블** 노드.

## <a name="work-with-blob-resources"></a>Blob 리소스로 작업

합니다 **Blob** 노드에 선택한 저장소 계정에 대 한 컨테이너 목록이 표시 됩니다. Blob 컨테이너에 blob 파일 및 폴더와 하위 폴더에 이러한 blob을 구성할 수 있습니다. 자세한 내용은 [.NET에서 Blob storage를 사용 하는 방법을](/azure/storage/blobs/storage-dotnet-how-to-use-blobs)합니다.

### <a name="to-create-a-blob-container"></a>Blob 컨테이너를 만들려면

1. 바로 가기 메뉴를 열고 합니다 **Blob** 노드를 선택한 후 **Blob 컨테이너 만들기**합니다.
1. 에 **Blob 컨테이너 만들기** 대화 상자에서 새 컨테이너의 이름을 입력 합니다.  
1. 키보드에서 Enter를 선택를 클릭 하거나 저장할 blob 컨테이너 이름 필드 외부를 눌러서 수 있습니다.

   > [!NOTE]
   > Blob 컨테이너 이름은 숫자 (0-9) 또는 소문자 (a – z)를 사용 하 여 시작 해야 합니다.

### <a name="to-delete-a-blob-container"></a>Blob 컨테이너를 삭제 하려면

를 제거 하 고 선택 하려는 blob 컨테이너에 대 한 바로 가기 메뉴를 열고 **삭제**합니다.

### <a name="to-display-a-list-of-the-items-in-a-blob-container"></a>Blob 컨테이너에 있는 항목의 목록을 표시 하려면

목록에서 blob 컨테이너 이름의 바로 가기 메뉴를 열고 선택한 **열려**합니다.

Blob 컨테이너의 콘텐츠를 볼 때 blob 컨테이너 보기 라는 탭에 표시 됩니다.

![Blob 컨테이너 보기](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC749016.png)

Blob 컨테이너 보기의 오른쪽 위 모퉁이의 단추를 사용 하 여 blob에서 다음 작업을 수행할 수 있습니다.

* 필터 값을 입력 하 고 적용 합니다.
* 컨테이너의 blob 목록을 새로 고칩니다.
* 파일을 업로드 합니다.
* Blob을 삭제 합니다. (기본 파일은 삭제 되지 않습니다 blob 컨테이너에서 파일을 삭제 합니다. 만 제거 하는 blob 컨테이너에서 됩니다.)
* Blob을 엽니다.
* 로컬 컴퓨터에 blob을 저장 합니다.

### <a name="to-create-a-folder-or-subfolder-in-a-blob-container"></a>Blob 컨테이너에 폴더 또는 하위 폴더를 만들려면

1. 클라우드 탐색기에서 blob 컨테이너를 선택 합니다. 컨테이너 창에서 선택 합니다 **Blob 업로드** 단추입니다.

1. 에 **새 파일 업로드** 대화 상자에서를 **찾아보기** 를 업로드 하려는 파일을 지정 하려면 단추를 한 후에 폴더 이름을 입력 합니다 **폴더 (선택 사항)** 상자.

   ![Blob 폴더에 파일을 업로드합니다.](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766037.png)

   같은 단계를 수행 하 여 컨테이너 폴더에 하위 폴더를 추가할 수 있습니다. 폴더 이름을 지정 하지 않으면, blob 컨테이너의 최상위 수준에 파일이 업로드 됩니다. 파일은 컨테이너에 지정된 된 폴더에 나타납니다.

   ![Blob 컨테이너에 폴더 추가](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766038.png)

1. 폴더를 두 번 클릭 하거나 폴더의 내용을 확인 하려면 enter 키를 선택 합니다. 컨테이너의 폴더에 있는 경우 이동할 수 있습니다 다시 컨테이너의 루트를 선택 하 여 합니다 **부모 디렉터리 열기** (화살표) 단추입니다.

### <a name="to-delete-a-container-folder"></a>컨테이너 폴더를 삭제 하려면

폴더에 있는 모든 파일을 삭제 합니다.

Blob 컨테이너의 폴더는 가상 폴더 이기 때문에 빈 폴더를 만들 수 없습니다. 또한 파일 콘텐츠를 삭제 하려면 폴더를 삭제할 수 없습니다 하 하지만 폴더 자체를 삭제 하려면 폴더의 전체 내용을 삭제 합니다.

### <a name="to-filter-blobs-in-a-container"></a>컨테이너의 blob를 필터링 하려면

공통 접두사를 지정 하 여 표시 되는 blob를 필터링 할 수 있습니다.

예를 들어 접두사를 입력 하는 경우 **hello** 에서 필터 텍스트 상자를 선택 합니다 합니다 **Execute** (**!**) 단추를 "hello"로 시작 하는 blob만 나타납니다.

![필터 텍스트 상자](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC519076.png)

필터 텍스트 상자는 대/소문자 구분 및 와일드 카드 문자 필터링을 지원 하지 않습니다. Blob은 접두사로 필터링 할 수 있습니다. 접두사는 구분 기호를 사용 하 여 가상 계층에 blob을 구성 하는 경우 구분 기호를 포함할 수 있습니다. 접두사로 필터링 예를 들어, "HelloFabric /" 문자열을 사용 하 여 시작 하는 모든 blob을 반환 합니다.

### <a name="to-download-blob-data"></a>Blob 데이터를 다운로드 하려면

클라우드 탐색기에서 다음 방법 중 하나를 사용 합니다.

* 하나 이상의 blob에 대 한 바로 가기 메뉴를 열고 선택한 **열려**합니다.
* Blob 이름을 선택 하 고 다음을 선택 합니다 **열려** 단추입니다.
* Blob 이름을 두 번 클릭 합니다.

blob 다운로드 진행률이 표시 되는 **Azure 활동 로그** 창입니다.

Blob는 해당 파일 형식에 대 한 기본 편집기에서 열립니다. 운영 체제 파일 형식을 인식 하는 경우 로컬에 설치 된 응용 프로그램에서 파일이 열립니다. 그렇지 않으면 묻는 blob의 파일 형식에 대 한 적절 한 응용 프로그램을 선택 합니다. Blob을 다운로드할 때 생성 되는 로컬 파일 읽기 전용으로 표시 됩니다.

Blob 데이터는 로컬로 캐시 되 고 Azure Blob storage에서 blob의 마지막 수정 시간에 대해 확인 합니다. 마지막으로 다운로드 된 후 blob 업데이트 된 경우 다시 다운로드 됩니다. 그렇지 않은 경우 blob은 로컬 디스크에서 로드 됩니다.

기본적으로 blob은 임시 디렉터리에 다운로드 됩니다. 특정 디렉터리에 blob을 다운로드 하려면 선택한 blob 이름에 대 한 바로 가기 메뉴를 열고 선택한 **다른 이름으로 저장**합니다. 이 방식으로 blob을 저장 하면 blob 파일이 열리지 않고 및 로컬 파일 읽기/쓰기 특성으로 생성 됩니다.

### <a name="to-upload-blobs"></a>Blob을 업로드 하려면

Blob을 업로드 하려면 선택 합니다 **Blob 업로드** blob 컨테이너 보기에서 보도록 컨테이너가 열려 단추입니다.

하나 이상의 파일을 업로드 하려면 선택한 모든 형식의 파일을 업로드할 수 있습니다. 합니다 **Azure 활동 로그** 창 업로드의 진행률이 표시 됩니다. Blob 데이터를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [.NET에서 Azure Blob storage를 사용 하는 방법을](http://go.microsoft.com/fwlink/p/?LinkId=267911)합니다.

### <a name="to-view-logs-transferred-to-blobs"></a>Blob에 전송 된 로그를 보려면

Azure 응용 프로그램에서 데이터를 기록 하도록 Azure 진단을 사용 하는 저장소 계정에 로그를 전송 하는 경우 이러한 로그에 대해 Azure에서 만들어진 컨테이너가 표시 됩니다. Azure에 배포 된 경우에 특히 쉬운 응용 프로그램을 사용 하 여 문제를 식별 하는 서버 탐색기에서 이러한 로그를 확인 합니다.

Azure 진단에 대 한 자세한 내용은 참조 하세요. [Azure 진단을 사용 하 여 로깅 데이터 수집](https://msdn.microsoft.com/library/azure/gg433048.aspx)합니다.

### <a name="to-get-the-url-for-a-blob"></a>Blob에 대 한 URL을 가져오려면

Blob의 바로 가기 메뉴를 열고 선택한 **URL 복사**합니다.

### <a name="to-edit-a-blob"></a>Blob을 편집 하려면

Blob을 선택 하 고 다음을 선택 합니다 **Blob 열기** 단추입니다.

파일을 임시 위치로 다운로드 이며 로컬 컴퓨터에서 열립니다. 변경한 후 다시 blob을 업로드 합니다.

## <a name="work-with-queue-resources"></a>큐 리소스로 작업

Storage 서비스 큐는 Azure storage 계정에서 호스트 됩니다. 클라우드 서비스 역할이 메시지 전달 메커니즘에 의해 서로 및 다른 서비스와 통신할 수 있도록 사용할 수 있습니다. 외부 클라이언트에 대 한 웹 서비스 및 클라우드 서비스를 통해 큐를 프로그래밍 방식으로 액세스할 수 있습니다. 또한 Visual Studio에서 서버 탐색기를 사용 하 여 직접 큐에 액세스할 수 있습니다.

큐를 사용 하는 클라우드 서비스를 개발 하는 경우에 Visual Studio를 사용 하 여 큐를 만들고 개발 하 고 코드를 테스트 하는 대화형으로 작업 하는 것이 좋습니다.

서버 탐색기에서 수 저장소 계정에 큐를 보고, 큐를 삭제, 큐 메시지를 보기를 열어 만들고 큐에 메시지를 추가 합니다. 보기에 대 한 큐를 열 때 개별 메시지를 볼 수 있습니다 하 고 왼쪽 위 모퉁이의 단추를 사용 하 여 큐에서 다음 작업을 수행할 수 있습니다.

* 큐 보기를 새로 고칩니다.
* 큐에 메시지를 추가 합니다.
* 최상위 메시지를 큐에서 제거 합니다.
* 전체 큐를 지웁니다.

다음 이미지에서는 두 개의 메시지를 포함 하는 큐를 보여 줍니다.

![큐 보기](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC651470.png)

자세한 내용은 저장소 서비스 큐에 대 한 참조 [.NET을 사용 하 여 Azure Queue storage 시작](http://go.microsoft.com/fwlink/?LinkID=264702)합니다. 웹 서비스에 대 한 정보에 대 한 저장소 서비스 큐에 대 한 참조 [큐 서비스 개념](http://go.microsoft.com/fwlink/?LinkId=264788)합니다. Visual Studio를 사용 하 여 저장소 서비스 큐에 메시지를 보내는 방법에 대 한 자세한 내용은 [저장소 서비스 큐에 메시지 보내기](https://docs.microsoft.com/azure/visual-studio/vs-storage-cloud-services-getting-started-queues)합니다.

> [!NOTE]
> 저장소 서비스 큐는 Azure Service Bus 큐와에서 구별 됩니다. Service Bus 큐에 대 한 자세한 내용은 참조 하세요. [Service Bus 큐, 토픽 및 구독](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-queues-topics-subscriptions)합니다.

## <a name="work-with-table-resources"></a>테이블 리소스로 작업

Azure Table storage는 다량의 구조화 된 데이터를 저장합니다. 이 서비스는 Azure 클라우드 내부 및 외부에서 인증 된 호출을 허용 하는 NoSQL 데이터 저장소. Azure 테이블은 구조화 된 비관계형 데이터를 저장 하기에 적합 합니다.

### <a name="to-create-a-table"></a>테이블을 만들려면

1. 클라우드 탐색기에서 선택 합니다 **테이블** 한 다음 선택한 저장소 계정에 대 한 노드의 **Create Table**합니다.
1. 에 **Create Table** 대화 상자에서 테이블의 이름을 입력 합니다.

### <a name="to-view-table-data"></a>테이블 데이터를 보려면

1. 클라우드 탐색기에서 엽니다는 **Azure** 노드를 연 다음 합니다 **저장소** 노드.
1. 관심 있는 열고는 저장소 계정 노드를 엽니다는 **테이블** 노드에서 저장소 계정의 테이블 목록을 볼 수 있습니다.
1. 테이블에 대 한 바로 가기 메뉴를 열고 선택한 **뷰 테이블**합니다.

    ![솔루션 탐색기에서 Azure 테이블](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC744165.png)

테이블은 엔터티 (행에 표시) 및 속성 (열에 표시) 별로 구성 됩니다. 예를 들어, 다음 그림은 테이블 디자이너에 나열 된 엔터티를 보여 줍니다.

### <a name="to-edit-table-data"></a>테이블 데이터를 편집 하려면

테이블 디자이너에서 엔터티 (단일 행) 또는 속성 (단일 셀)에 대 한 바로 가기 메뉴를 열고 선택한 **편집**합니다.

    ![Add or edit a table entity](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC656238.png)

단일 테이블에서 엔터티 속성 (열)의 동일한 집합을 가질 필요가 없습니다. 테이블 데이터 보기 및 편집에 대 한 다음과 같은 제한에 유의 하십시오.

* 이진 데이터 편집 하거나 볼 수 없습니다 (`type byte[]`), 없지만 테이블에 저장할 수 있습니다.
* 편집할 수 없습니다는 **PartitionKey** 또는 **RowKey** 값, azure에서 Table storage 작업을 지원 하지 않기 때문입니다.
* 라는 속성을 만들 수 없습니다 **타임 스탬프**합니다. Azure storage 서비스는 해당 이름을 가진 속성을 사용합니다.
* 입력 하는 경우는 **날짜/시간** 값 따라야 컴퓨터의 지역 및 언어 설정에 부합 되는 형식 (hh: MM/DD/YYYY mm: 예를 들어 [AM | PM] 영어 (미국)에 대 한).

### <a name="to-add-entities"></a>엔터티를 추가하려면

1. 테이블 디자이너에서 선택 합니다 **엔터티 추가** 단추입니다.

    ![엔터티 추가 단추](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC655336.png)

1. 에 **엔터티 추가** 대화 상자에서 값을 입력 합니다 **PartitionKey** 및 **RowKey** 속성.

    ![엔터티 추가 대화 상자](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC655335.png)

    신중 하 게 값을 입력 합니다. 엔터티를 삭제 하 고 다시 추가 하지 않는 한 대화 상자를 닫은 후 변경할 수 있습니다.

### <a name="to-filter-entities"></a>엔터티를 필터링 하려면

쿼리 작성기를 사용 하는 경우 테이블에 표시 되는 엔터티 집합을 사용자 지정할 수 있습니다.

1. 쿼리 작성기를 열려면 보려는 테이블을 엽니다.
1. 선택 된 **쿼리 작성기** 테이블 보기의 도구 모음에서 단추입니다.

    합니다 **쿼리 작성기** 대화 상자가 나타납니다. 다음 그림에서는 쿼리 작성기에서 작성 중인 쿼리를 보여 줍니다.

    ![쿼리 작성기](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC652231.png)
1. 완료 되 면 쿼리 작성 대화 상자를 닫습니다. 쿼리의 결과 텍스트 형식이 WCF Data Services 필터로 텍스트 상자에 나타납니다.
1. 쿼리를 실행 하려면 녹색 삼각형 아이콘을 선택 합니다.

표시 되는 테이블 디자이너에서 입력 하는 경우 필터 텍스트 상자에 직접 WCF Data Services 필터 문자열을 엔터티 데이터를 필터링 할 수도 있습니다. 이 종류의 문자열은 SQL WHERE 절과 유사 하지만 HTTP 요청으로 서버에 전송 됩니다. 필터 문자열을 생성 하는 방법에 대 한 정보를 참조 하세요 [테이블 디자이너에 대 한 필터 문자열 Constructing](https://docs.microsoft.com/azure/vs-azure-tools-table-designer-construct-filter-strings)합니다.

다음 그림에서는 유효한 필터 문자열의 예를 보여 줍니다.

![필터 문자열](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC655337.png)

## <a name="refresh-storage-data"></a>저장소 데이터 새로 고침

서버 탐색기에 연결 하거나 저장소 계정에서 데이터를 가져옵니다을 때 작업을 걸릴 수 있습니다 잠시 완료 합니다. 서버 탐색기를 연결할 수 없는 경우 작업 시간이 초과 될 수 있습니다. 데이터를 검색 하는 동안 Visual Studio의 다른 부분에서 작업을 계속할 수 있습니다. 파일을 너무 오래 걸리는 경우 작업을 취소 하려면 선택 합니다 **새로 고침 중지** 서버 탐색기 도구 모음 단추입니다.

### <a name="to-refresh-blob-container-data"></a>Blob 컨테이너 데이터를 새로 고치려면

* 선택는 **Blob** 아래에 있는 노드 **저장소**를 선택한 후는 **새로 고침** 서버 탐색기 도구 모음 단추.
* 표시 되는 blob 목록 새로 고침을 선택 합니다 **Execute** 단추입니다.

### <a name="to-refresh-table-data"></a>테이블 데이터를 새로 고치려면

* 선택는 **테이블** 아래에 있는 노드 **저장소**를 선택한 후는 **새로 고침** 서버 탐색기 도구 모음 단추.
* 테이블 디자이너에 표시 되는 엔터티 목록을 새로 고치려면를 선택 합니다 **Execute** 테이블 디자이너에서 단추입니다.

### <a name="to-refresh-queue-data"></a>큐 데이터를 새로 고치려면

선택는 **큐** 아래에 있는 노드 **저장소**를 선택한 후는 **새로 고침** 서버 탐색기 도구 모음 단추.

### <a name="to-refresh-all-items-in-a-storage-account"></a>저장소 계정에 모든 항목을 새로 고치려면

계정 이름을 선택한 다음 선택 합니다 **새로 고침** 서버 탐색기 도구 모음 단추입니다.

## <a name="add-storage-accounts-by-using-server-explorer"></a>서버 탐색기를 사용 하 여 저장소 계정 추가

서버 탐색기를 사용 하 여 저장소 계정을 추가 하는 방법은 두 가지가 있습니다. Azure 구독에서 저장소 계정을 만들거나 기존 저장소 계정을 연결할 수 있습니다.

### <a name="to-create-a-storage-account-by-using-server-explorer"></a>서버 탐색기를 사용 하 여 저장소 계정을 만들려면

1. 서버 탐색기에서 바로 가기 메뉴를 열고 합니다 **저장소** 노드를 선택한 후 **Storage 계정 만들기**합니다.

1. 에 **Storage 계정 만들기** 대화 상자에서 선택 하거나 다음 정보를 입력 합니다.

   * 저장소 계정을 추가할 Azure 구독입니다.
   * 새 저장소 계정에 사용 하려는 이름입니다.
   * 지역 또는 선호도 그룹 (예: 미국 서 부 또는 동남 아시아)입니다.
   * 복제와 같은 저장소 계정에 대해 사용 하려는 형식의 로컬 중복 됩니다.

   ![Azure storage 계정 만들기](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC744166.png)

1. **만들기**를 선택합니다.

새 저장소 계정에 표시 된 **저장소** 솔루션 탐색기에서 목록입니다.

### <a name="to-attach-an-existing-storage-account-by-using-server-explorer"></a>서버 탐색기를 사용 하 여 기존 저장소 계정을 연결 하려면

1. 서버 탐색기에서 Azure에 대 한 바로 가기 메뉴를 열고 **스토리지** 노드를 선택한 후 **외부 저장소 연결**합니다.

    ![기존 저장소 계정을 추가합니다.](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766039.png)
1. 에 **Storage 계정 만들기** 대화 상자에서 선택 하거나 다음 정보를 입력 합니다.

   * 연결 하려는 기존 저장소 계정의 이름입니다.
   * 선택한 저장소 계정의 키입니다. 이 값은 저장소 계정을 선택할 때를 일반적으로 제공 됩니다. Visual Studio가 저장소 계정 키를 기억 하기를 원하면 선택 합니다 **계정 키 기억 하기** 확인란 합니다.
   * HTTP, HTTPS 또는 사용자 지정 끝점을 같은 저장소 계정에 연결 하는 데 사용 되는 프로토콜입니다. 사용자 지정 끝점에 대 한 자세한 내용은 참조 하세요. [연결 문자열을 구성 하는 방법을](https://msdn.microsoft.com/library/azure/ee758697.aspx)합니다.

### <a name="to-view-the-secondary-endpoints"></a>보조 끝점을 확인 하려면

사용 하 여 저장소 계정을 만든 경우 합니다 **읽기 액세스 지역 중복** 복제 옵션을 계정 이름에 대 한 바로 가기 메뉴를 열고 보조 끝점을 확인 하 고 다음 선택할 수 **속성**.

![저장소 보조 끝점](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766040.png)

### <a name="to-remove-a-storage-account-from-server-explorer"></a>서버 탐색기에서 저장소 계정을 제거 하려면

서버 탐색기에서 계정 이름에 대 한 바로 가기 메뉴를 열고 선택한 후 **삭제**합니다. 

저장소 계정을 삭제 하면 해당 계정에 대해 저장된 된 키 정보도 제거 됩니다.

서버 탐색기에서 저장소 계정을 삭제 하면 저장소 계정 또는 포함 된 모든 데이터 영향을 하지 않습니다. 단순히 서버 탐색기에서 참조를 제거합니다. 저장소 계정을 영구적으로 삭제 하려면 사용 합니다 [Azure portal](https://portal.azure.com/)합니다.

## <a name="next-steps"></a>다음 단계

Azure storage 서비스를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요 [Azure Storage 서비스 액세스](https://msdn.microsoft.com/library/azure/ee405490.aspx)합니다.
