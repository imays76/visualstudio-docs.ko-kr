---
title: 클라우드 서비스의 성능 테스트 | Microsoft Docs
description: Visual Studio 프로파일러를 사용 하 여 클라우드 서비스의 성능을 테스트 합니다.
author: mikejo5000
manager: douge
ms.assetid: 7a5501aa-f92c-457c-af9b-92ea50914e24
ms.topic: conceptual
ms.tgt_pltfrm: multiple
ms.workload: na
ms.date: 11/11/2016
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 25b60e5e4072a0523d17082a5c5646e5bb1ade6a
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002408"
---
# <a name="testing-the-performance-of-a-cloud-service"></a>클라우드 서비스의 성능 테스트
## <a name="overview"></a>개요
다음과 같은 방법으로 클라우드 서비스의 성능을 테스트할 수 있습니다.

* 요청 및 연결 하는 방법에 대 한 정보를 수집 하 고 서비스가 고객 관점에서 수행 하는 방법을 보여 주는 사이트 통계를 검토 하려면 Azure 진단을 사용 합니다. 시작, 참조 [Azure Cloud Services 및 Virtual Machines에서 진단 구성](http://go.microsoft.com/fwlink/p/?LinkId=623009)합니다.
* Visual Studio 프로파일러를 사용 하 여 서비스 실행 방식의 계산 측면의 자세한 분석을 가져옵니다. 이 항목에서 설명한 대로 Azure에서 실행 되는 서비스 성능을 측정 하기 위해 프로파일러를 사용할 수 있습니다. 서비스는 계산 에뮬레이터에서 로컬로 실행 될 때 성능을 측정 하기 위해 프로파일러를 사용 하는 방법에 대 한 정보를 참조 하세요. [Visual Studio Profiler계산에뮬레이터사용하여로컬로AzureCloudService의성능을테스트](http://go.microsoft.com/fwlink/p/?LinkId=262845).

## <a name="choosing-a-performance-testing-method"></a>성능 테스트 방법 선택
### <a name="use-azure-diagnostics-to-collect"></a>Azure 진단을 사용 하 여 수집 합니다.
* 웹 페이지 또는 요청 및 연결 등의 서비스에 대 한 통계입니다.
* 역할이 재시작 되는 빈도 같은 역할에 대 한 통계입니다.
* 전체 가비지 수집기를 사용 하는 시간 또는 메모리 백분율 등 메모리 사용에 대 한 정보는 실행 중인 역할의 집합입니다.

### <a name="use-the-visual-studio-profiler-to"></a>Visual Studio 프로파일러를 사용 합니다.
* 함수는 가장 많은 시간을 결정 합니다.
* 계산이 많은 프로그램의 각 파트는 얼마나 많은 시간을 측정 합니다.
* 서비스의 두 버전에 대 한 자세한 성능 보고서 비교 합니다.
* 메모리 할당의 개별 메모리 할당 수준 보다 좀 더 자세히 분석 합니다.
* 다중 스레드 코드에서 동시성 문제를 분석 합니다.

프로파일러를 사용 하면 클라우드 서비스를 로컬로 또는 Azure에서 실행 될 때 데이터를 수집할 수 있습니다.

### <a name="collect-profiling-data-locally-to"></a>로컬로 프로 파일링 데이터를 수집 합니다.
* 현실적인 시뮬레이션 된 부하를 필요 하지 않은 특정 작업자 역할의 실행 같은 클라우드 서비스의 일부 성능을 테스트 합니다.
* 격리 수준 제어 상태에서 클라우드 서비스의 성능을 테스트 합니다.
* Azure에 배포 하기 전에 클라우드 서비스의 성능을 테스트 합니다.
* 기존 배포를 방해 하지 않고 클라우드 서비스의 성능을 개인적으로 테스트 합니다.
* Azure에서 실행 하는 것에 대 한 요금이 발생 하지 않고 서비스의 성능을 테스트 합니다.

### <a name="collect-profiling-data-in-azure-to"></a>Azure에서 프로 파일링 데이터를 수집 합니다.
* 시뮬레이션 된 부 하나 실제 부하에서 클라우드 서비스의 성능을 테스트 합니다.
* 이 항목 뒷부분에 설명 된 대로 프로 파일링 데이터 수집의 계측 방법을 사용 합니다.
* 서비스가 프로덕션에서 실행 되는 경우와 동일한 환경에서 서비스의 성능을 테스트 합니다.

일반적으로 일반 클라우드 서비스를 테스트 하거나 심한 부하를 시뮬레이션합니다.

## <a name="profiling-a-cloud-service-in-azure"></a>Azure에서 클라우드 서비스를 프로 파일링
Visual Studio에서 클라우드 서비스를 게시할 때에 서비스를 프로 파일링 하 고 원하는 정보를 제공 하는 프로 파일링 설정을 지정할 수 있습니다. 역할의 각 인스턴스에 대 한 프로 파일링 세션 시작 됩니다. Visual Studio에서 서비스를 게시 하는 방법에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 Azure 클라우드 서비스에 게시](https://msdn.microsoft.com/library/azure/ee460772.aspx)합니다.

Visual Studio 성능 프로 파일링 하는 방법에 대 한 자세히 알아보려면 [초보자를 위한 성능 프로 파일링](https://msdn.microsoft.com/library/azure/ms182372.aspx) 하 고 [프로 파일링 도구를 사용 하 여 응용 프로그램 성능 분석](https://msdn.microsoft.com/library/azure/z9z62c29.aspx)합니다.

> [!NOTE]
> IntelliTrace 또는 클라우드 서비스를 게시할 때 프로 파일링을 사용할 수 있습니다. 둘 다를 사용할 수 없습니다.
> 
> 

### <a name="profiler-collection-methods"></a>Profiler 컬렉션 메서드
프로 파일링을 위해 성능 문제에 따라 여러 수집 방법을 사용할 수 있습니다.

* **CPU 샘플링** -이 방법은 CPU 이용률 문제의 초기 분석에 유용한 응용 프로그램 통계를 수집 합니다. CPU 샘플링은 대부분의 성능 조사를 시작할 때 좋은 방법입니다. CPU 샘플링 데이터를 수집할 때 프로 파일링 하는 응용 프로그램에 많은 영향을 미치지 않습니다.
* **계측** -이 방법은 집중된 분석 및 입/출력 성능 문제 분석에 유용한 자세한 타이밍 데이터를 수집 합니다. 계측 방법을 프로 파일링 실행 중 모듈의 각 항목, 종료 및 함수 호출 함수를 기록 합니다. 이 방법은 코드의 한 섹션에 대한 자세한 타이밍 정보를 수집하고 입력 및 출력 작업이 응용 프로그램 성능에 미치는 영향을 이해하는 데 유용합니다. 이 메서드는 32 비트 운영 체제를 실행 하는 컴퓨터에 대 한 비활성화 됩니다. 이 옵션을 실행할 때만 클라우드 서비스를 Azure에 로컬이 아닌 계산 에뮬레이터에서 사용할 수 있습니다.
* **.NET 메모리 할당** -이 방법은 샘플링 프로 파일링 방법을 사용 하 여.NET Framework 메모리 할당 데이터를 수집 합니다. 수집 된 데이터는 할당 된 개체의 크기와 수를 포함합니다.
* **동시성** -이 방법은 리소스 경합 데이터 및 멀티스레드와 멀티 프로세스 응용 프로그램을 분석 하는 데 도움이 되는 프로세스 및 스레드 실행 데이터를 수집 합니다. 동시성 방법은 스레드가 해제될 응용 프로그램 리소스에 대한 잠긴 액세스에 대해 대기하는 경우와 같은 코드의 실행을 차단하는 각 이벤트에 대한 데이터를 수집합니다. 이 메서드는 다중 스레드 응용 프로그램을 분석하는 데 유용합니다.
* 설정할 수도 있습니다 **계층 상호작용 프로 파일링**, 동기 ADO.NET의 실행 시간에 대 한 추가 정보를 제공 하는 하나 이상의 데이터베이스와 통신 하는 다중 계층 응용 프로그램의 함수에서 호출 합니다. 프로 파일링 방법 중 하나를 사용 하 여 계층 상호 작용 데이터를 수집할 수 있습니다. 계층 상호작용 프로 파일링 하는 방법에 대 한 자세한 내용은 참조 하세요. [계층 상호 작용 뷰](https://msdn.microsoft.com/library/azure/dd557764.aspx)합니다.

## <a name="configuring-profiling-settings"></a>프로 파일링 설정 구성
다음 그림에는 Azure 응용 프로그램 게시 대화 상자에서 프로 파일링 설정을 구성 하는 방법을 보여 줍니다.

![프로파일링 설정 구성](./media/vs-azure-tools-performance-profiling-cloud-services/IC526984.png)

> [!NOTE]
> 사용 하도록 설정 합니다 **프로 파일링** 확인란 프로파일러가 클라우드 서비스를 게시 하는 데 사용 하는 로컬 컴퓨터에 설치 되어 있어야 합니다. 기본적으로 프로파일러는 Visual Studio를 설치할 때 설치 됩니다.
> 
> 

### <a name="to-configure-profiling-settings"></a>프로 파일링 설정을 구성 하려면
1. 솔루션 탐색기에서 Azure 프로젝트에 대 한 바로 가기 메뉴를 열고 선택한 후 **게시**합니다. 클라우드 서비스를 게시 하는 방법에 대 한 자세한 단계를 참조 하세요 [Azure tools를 사용 하 여 클라우드 서비스 게시](http://go.microsoft.com/fwlink/p?LinkId=623012)합니다.
2. 에 **Azure 응용 프로그램 게시** 대화 상자에서 선택한 합니다 **고급 설정** 탭 합니다.
3. 프로 파일링을 사용 하려면 선택 합니다 **프로 파일링** 확인란 합니다.
4. 에 프로 파일링 설정을 구성 하려면 선택 합니다 **설정을** 하이퍼링크입니다. 프로 파일링 설정 대화 상자가 나타납니다.
5. **프로 파일링을 사용 하 시겠습니까** 옵션 단추를 해야 하는 프로 파일링 유형을 선택 합니다.
6. 계층 상호작용 프로 파일링 데이터를 수집 하려면 선택 합니다 **계층 상호 작용 프로 파일링 사용** 확인란 합니다.
7. 설정을 저장 하려면 선택 합니다 **확인** 단추입니다.
   
    이 응용 프로그램을 게시할 때 각 역할에 대 한 프로 파일링 세션을 만들려면 이러한 설정이 사용 됩니다.

## <a name="viewing-profiling-reports"></a>프로 파일링 보고서 보기
프로 파일링 세션은 클라우드 서비스에서 역할의 각 인스턴스에 대해 생성 됩니다. Visual Studio에서 각 세션의 프로 파일링 보고서를 보려면 서버 탐색기 창에서 볼 수 있으며 그런 다음 역할의 인스턴스를 선택 하려면 Azure Compute 노드를 선택 키를 누릅니다. 다음 그림에 나와 있는 것 처럼 프로 파일링 보고서를 볼 수 있습니다.

![Azure에서 프로 파일링 보고서 보기](./media/vs-azure-tools-performance-profiling-cloud-services/IC748914.png)

### <a name="to-view-profiling-reports"></a>프로 파일링 보고서 보기
1. Visual Studio에서 서버 탐색기 창을 보려면 메뉴 모음에서 보기 서버 탐색기를 선택 합니다.
2. Azure Compute 노드를 선택 하 고 Visual Studio에서 게시할 때 프로 파일링 하도록 선택한 클라우드 서비스에 대 한 Azure 배포 노드를 선택 합니다.
3. 인스턴스에 대 한 프로 파일링 보고서를 보려면 서비스에서 역할을 선택 합니다. 특정 인스턴스에 대 한 바로 가기 메뉴를 열고 선택한 **프로 파일링 보고서 보기**합니다.
   
    .Vsp 파일인 보고서가 이제 Azure에서 다운로드 하 고 Azure 활동 로그에 다운로드 상태가 표시 됩니다. 다운로드 완료 되 면 프로 파일링 보고서 라는 Visual Studio 편집기에서 탭에 나타납니다 <Role name> *<Instance Number>* <identifier>.vsp 합니다. 보고서에 대 한 요약 데이터가 표시 됩니다.
4. 현재 보기 목록에서 보고서의 다른 뷰를 표시 하려면 원하는 뷰 형식을 선택 합니다. 자세한 내용은 [프로 파일링 도구 보고서 뷰](https://msdn.microsoft.com/library/azure/bb385755.aspx)합니다.

## <a name="next-steps"></a>다음 단계
[Cloud Services 디버깅](https://msdn.microsoft.com/library/azure/ee405479.aspx)

[Visual Studio에서 Azure 클라우드 서비스에 게시](https://msdn.microsoft.com/library/azure/ee460772.aspx)

