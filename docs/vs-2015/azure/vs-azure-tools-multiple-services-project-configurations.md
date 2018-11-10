---
title: 여러 서비스 구성을 사용 하 여 Azure 프로젝트 구성 | Microsoft Docs
description: ServiceDefinition.csdef, ServiceConfiguration.Local.cscfg 및 ServiceConfiguration.Cloud.cscfg 파일을 변경 하 여 Azure 클라우드 서비스 프로젝트를 구성 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: a4fb79ed-384f-4183-9f74-5cac257206b9
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2017
ms.author: ghogen
ms.openlocfilehash: f309c2a960d011601a9fdd41e29d767c667de838
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002933"
---
# <a name="configuring-your-azure-project-in-visual-studio-to-use-multiple-service-configurations"></a>여러 서비스 구성을 사용하도록 Visual Studio에서 Azure 프로젝트 구성

Visual Studio에서 Azure 클라우드 서비스 프로젝트를 포함 세 개의 구성 파일: `ServiceDefinition.csdef`, `ServiceConfiguration.Local.cscfg`, 및 `ServiceConfiguration.Cloud.cscfg`:

- `ServiceDefinition.csdef` 클라우드 서비스 및 해당 역할의 요구 사항을 설명 하 고 모든 인스턴스에 적용 되는 설정을 제공 하려면 Azure에 배포 됩니다. Azure 서비스 호스팅 런타임 API를 사용 하 여 런타임에 설정은 읽을 수 있습니다. Azure에서 클라우드 서비스를 중지 하는 경우에이 파일을 업데이트할 수 있습니다.
- `ServiceConfiguration.Local.cscfg` 및 `ServiceConfiguration.Cloud.cscfg` 정의에서 설정 파일 및 각 역할에 대해 실행할 인스턴스 수를 지정에 대 한 값을 제공 합니다. 로컬 디버깅에 사용 되는 값을 포함 하는 "Local" 파일 "클라우드" 파일을 Azure로 배포 된 `ServiceConfiguration.cscfg` 서버 환경에 대 한 설정을 제공 합니다. 클라우드 서비스는 Azure에서 실행 되는 동안이 파일을 업데이트할 수 있습니다.

구성 파일은 관리 되 고 해당 역할에 대 한 속성 페이지를 사용 하 여 Visual Studio에서 수정 (역할을 마우스 오른쪽 단추로 클릭 **속성**, 역할을 두 번 클릭). 선택한 구성 변경 내용을 범위로 축소할 수 있습니다 합니다 **서비스 구성** 드롭 다운 합니다. 웹 및 작업자 역할에 대 한 속성은 마찬가지로 제외 하 고 다음 섹션에 설명 된 것입니다.

![VS_Solution_Explorer_Roles_Properties](./media/vs-azure-tools-multiple-services-project-configurations/IC784076.png)

서비스 정 및 서비스 구성 파일에 대 한 기본 스키마에 대 한 정보를 참조 하세요. 합니다 [.csdef XML 스키마](/azure/cloud-services/schema-csdef-file.md) 하 고 [.cscfg XML 스키마](/azure/cloud-services/schema-cscfg-file.md) 문서입니다. 서비스 구성에 대 한 자세한 내용은 참조 하세요. [Cloud Services를 구성 하는 방법을](/azure/cloud-services/cloud-services-how-to-configure-portal)합니다.


## <a name="configuration-page"></a>구성 페이지

### <a name="service-configuration"></a>서비스 구성

선택 `ServiceConfiguration.*.cscfg` 변경으로 영향을 받는 파일입니다. 기본적으로 로컬 및 클라우드 변형이 있으며 사용할 수는 **관리 하는 중...**  복사, 이름 바꾸기, 구성 파일을 제거 하는 명령입니다. 이러한 파일에 클라우드 서비스 프로젝트에 추가 되 고 나타나지 **솔루션 탐색기**합니다. 그러나 이름 바꾸기 또는 구성을 제거 합니다.이 컨트롤 에서만에서 수행할 수 있습니다.

### <a name="instances"></a>인스턴스

설정 된 **인스턴스** 속성을이 역할에 대 한 서비스를 실행 하는 인스턴스 수를 계산 합니다.

설정 합니다 **VM 크기** 속성을 **작음**, **작은**, **중간**, **대형**, 또는 **초대형**합니다.  자세한 내용은 [Cloud Services 크기](/azure/cloud-services/cloud-services-sizes-specs)합니다.

### <a name="startup-action-web-role-only"></a>시작 작업 (웹 역할에만 해당)

Visual Studio가 디버깅을 시작할 때 HTTP 끝점 또는 HTTPS 끝점 또는 둘 다에 대 한 웹 브라우저를 시작 하도록이 속성을 설정 합니다.

합니다 **HTTPS 끝점** 옵션은 역할에 대 한 HTTPS 엔드포인트를 이미 정의한 경우에 사용할 수 있습니다. HTTPS 끝점을 정의할 수는 **끝점** 속성 페이지.

HTTPS 끝점을 이미 추가한 경우 기본적으로 HTTPS 끝점 옵션은 사용 및 Visual Studio가 디버깅을 시작 하면 HTTP 끝점에 대 한 브라우저 외에도 두 시작 옵션이 설정 된 것으로 가정 하는 경우이 끝점에 대 한 브라우저를 시작 합니다.

### <a name="diagnostics"></a>진단

기본적으로 웹 역할에 대 한 진단은 사용할 수 있습니다. Azure 클라우드 서비스 프로젝트 및 저장소 계정은 로컬 저장소 에뮬레이터를 사용 하도록 설정 됩니다. Azure에 배포할 준비가 되었을 때 작성기 단추를 선택할 수 있습니다 (**...** ) 대신 Azure storage를 사용 하도록 합니다. 요청 시 또는 자동으로 예약 된 간격으로 저장소 계정에 진단 데이터를 전송할 수 있습니다. Azure 진단에 대 한 자세한 내용은 참조 하세요. [Azure Cloud Services 및 Virtual Machines에서 진단 사용](/azure/cloud-services/cloud-services-dotnet-diagnostics)합니다.

## <a name="settings-page"></a>설정 페이지

에 **설정을** 페이지에서 이름-값 쌍으로 구성 설정을 추가할 수 있습니다. 역할에서 실행 되는 코드에서 제공 하는 클래스를 사용 하 여 런타임에 구성 설정의 값을 읽을 수는 [Azure Managed Library](http://go.microsoft.com/fwlink?LinkID=171026), 특히 합니다 [GetConfigurationSettingValue](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleenvironment.getconfigurationsettingvalue.aspx) 메서드.

### <a name="configuring-a-connection-string-for-a-storage-account"></a>저장소 계정에 대 한 연결 문자열 구성

연결 문자열은 저장소 에뮬레이터 또는 Azure storage 계정에 대 한 연결 및 인증 정보를 제공 하는 설정입니다. 역할의 코드가 Azure storage (blob, 큐 또는 테이블)에 액세스할 때마다 연결 문자열이 필요 합니다.

> [!Note]
> Azure storage 계정에 대 한 연결 문자열은 정의 된 형식을 사용 해야 합니다 (참조 [Azure Storage 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)).

클라우드 서비스 응용 프로그램을 배포 하는 경우 Azure storage 계정에 설정한 필요에 따라 로컬 저장소를 사용 하는 연결 문자열을 설정할 수 있습니다. 연결 문자열을 제대로 설정 하지 못했습니다 역할을 시작으로 설정 하지 않거나 초기화, 사용 중 및 중지 중 상태를 순환 하려면 발생할 수 있습니다.

연결 문자열을 만들려면 **설정 추가** 설정 **형식** "연결 문자열"입니다.

기존 또는 새 연결 문자열에 대 한 선택 **...** *의 오른쪽에는 **값** 열려는 필드를 **저장소 연결 문자열 만들기** 대화 상자:

1. 아래 **사용 하 여 연결**를 선택 합니다 **구독의** 구독에서 저장소 계정을 선택 하는 옵션입니다. Visual Studio에서 자동으로 저장소 계정 자격 증명을 획득 합니다 `.publishsettings` 파일입니다.
1. 선택 **수동으로 입력 한 자격 증명** 계정 이름을 지정 하 고 Azure portal에서 정보를 사용 하 여 직접 키 수 있습니다. 계정 키를 복사 합니다.
    1. Azure 포털 및 선택한 저장소 계정으로 이동 **키 관리**합니다.
    1. 계정 키를 복사 하려면 선택는 Azure portal에서 저장소 계정으로 이동 **설정 > 액세스 키**, 그런 다음 복사 단추를 사용 하 여 기본 액세스 키를 클립보드에 복사할 합니다.
1. 연결 옵션 중 하나를 선택 합니다. **사용자 지정 끝점 지정** 큐 및 blob, 테이블에 대 한 특정 Url을 지정 하도록 요청 합니다. 사용자 지정 끝점을 사용 하면 사용할 수 있도록 [사용자 지정 도메인](/azure/storage/blobs/storage-custom-domain-name.md) 액세스를 보다 정확 하 게 제어할 수 있습니다. 참조 [Azure Storage 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)합니다.
1. 선택 **확인**, 한 다음 **파일 > 저장** 새 연결 문자열을 사용 하 여 구성을 업데이트 합니다.

마찬가지로 응용 프로그램을 Azure에 게시할 때 Azure storage 계정 연결 문자열에 포함 된 서비스 구성을 선택 합니다. 응용 프로그램을 게시 한 후 응용 프로그램이 Azure storage 서비스에 대해 예상 대로 작동 하는지 확인 합니다.

서비스 구성을 업데이트 하는 방법에 대 한 자세한 내용은 섹션을 참조 하세요 [저장소 계정에 대 한 연결 문자열 관리](vs-azure-tools-configure-roles-for-cloud-service.md#manage-connection-strings-for-storage-accounts)합니다.

## <a name="endpoints-page"></a>끝점 페이지

웹 역할은 일반적으로 포트 80에서 단일 HTTP 엔드포인트를에 합니다. 반면에 작업자 역할에 임의 개수의 HTTP, HTTPS 또는 TCP 끝점이 있습니다. 끝점에서 외부 클라이언트에 사용할 수 있는 입력된 끝점 또는 서비스에서 실행 되는 다른 역할에 사용할 수 있는 내부 끝점일 수 있습니다.

- HTTP 끝점을 사용할 수 있도록 외부 클라이언트와 웹 브라우저에서 끝점 유형을 입력으로 변경 하 고 이름 및 공용 포트 번호를 지정 합니다.
- HTTPS 끝점을 사용할 수 있도록 외부 클라이언트와 웹 브라우저를 변경 하려면 끝점 유형을 **입력**, 이름, 공용 포트 번호 및 관리 인증서 이름을 지정 합니다. 인증서에도 정의 해야 합니다 **인증서** 관리 인증서를 지정 하려면 먼저 속성 페이지. 
- 끝점에 게 제공 내부 액세스에 대 한 클라우드 서비스의 다른 역할에서 끝점 유형을 내부로 변경 하 고 이름 및이 끝점에 대 한 가능한 개인 포트를 지정 합니다.

## <a name="local-storage-page"></a>로컬 저장소 페이지

사용할 수는 **로컬 저장소** 속성 페이지를 역할에 대 한 하나 이상의 로컬 저장소 리소스를 예약 합니다. 로컬 저장소 리소스는 역할 인스턴스의 실행 되는 Azure 가상 머신의 파일 시스템에서 예약된 된 디렉터리.

## <a name="certificates-page"></a>인증서 페이지

합니다 **인증서** 속성 페이지에 서비스 구성에 인증서에 대 한 정보를 추가 합니다. 인증서 서비스;와 함께 패키징되 지 않습니다 참고 통해 Azure에 별도로 인증서를 업로드 해야 합니다 [Azure portal](http://portal.azure.com)합니다.

여기서는 인증서를 추가 합니다. 서비스 구성에 인증서에 대 한 정보를 추가 합니다. 인증서는 서비스를 사용 하 여 패키지 되지 않습니다. Azure portal 통해 별도로 인증서를 업로드 해야 합니다.

인증서와 역할에 연결 하려면 인증서의 이름을 제공 합니다. 이 이름을 사용에서 HTTPS 끝점을 구성할 때 인증서를 참조 하는 **끝점** 페이지입니다. 다음으로, 인증서 저장소 인지를 지정 **로컬 컴퓨터** 하거나 **현재 사용자** 및 저장소의 이름입니다. 마지막으로, 인증서의 지문을 입력 합니다. 인증서는 현재 사용자 \ 개인 (내) 저장소에 있으면 채워진된 목록에서 인증서를 선택 하 여 인증서의 손도장을 입력할 수 있습니다. 다른 위치에 상주 하는 경우 지문 값을 직접 입력 합니다.

인증서 저장소에서 인증서를 추가 하면 모든 중간 인증서를 구성 설정으로 자동 추가 됩니다. 또한 이러한 중간 인증서는 SSL에 대 한 서비스를 올바르게 구성 하기 위해 Azure에 업로드 해야 합니다.

서비스를 사용 하 여 연결 하는 모든 관리 인증서는 클라우드에서 실행 되는 경우에 서비스에 적용 됩니다. 서비스를 로컬 개발 환경에서 실행 하는 경우 계산 에뮬레이터에서 관리 되는 표준 인증서를 사용 합니다.
