---
title: Visual Studio에서 부하 테스트 시나리오 편집 | Microsoft Docs
ms.date: 10/03/2016
ms.topic: article
helpviewer_keywords:
- load tests, scenarios
- load tests, user activities
- load tests, modeling scenarios
ms.assetid: fec04f2e-bf38-4d44-b2ec-fa50f58fd0d9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 5b4abcb0b75e379df360c045527790a708c55c6e
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="edit-load-test-scenarios"></a>부하 테스트 시나리오 편집

부하 테스트 *시나리오*는 부하 패턴, 테스트 조합, 브라우저 조합 및 네트워크 조합을 지정합니다. 시나리오는 복잡하고 현실적인 워크로드를 시뮬레이션하는 테스트를 구성할 수 있어 중요합니다.

예를 들어, 다양한 연결 속도로 각기 다른 브라우저를 사용하여 동시에 방문하고 있는 수백 명의 고객이 사용하는 인터넷 프런트 엔드가 있는 전자 상거래 사이트를 테스트할 수 있습니다. 내부 직원이 제품을 업데이트하고 통계를 보는 데 사용하는 관리 기능이 같은 사이트에 있을 수 있습니다. 이러한 내부 사용자는 주로 같은 브라우저와 고속 LAN 연결을 사용하여 사이트에 액세스합니다. 서로 다른 두 사용자 그룹의 속성을 다른 시나리오에 캡슐화할 수 있습니다. 각 시나리오는 가상 사용자 형식을 포함할 수 있습니다. 이 경우에는 가상 고객을 나타내는 부하 테스트 시나리오와 웹 사이트의 가상 내부 사용자를 나타내는 또 다른 시나리오를 만들 수 있습니다.

## <a name="scenario-components"></a>시나리오 구성 요소

부하 테스트를 만들 때 지정하는 모든 초기 구성 옵션과 설정은 나중에 부하 테스트 편집기에서 수정할 수 있습니다. 또한 부하 테스트에 새 시나리오, 실행 설정 및 카운터 집합을 추가할 수 있습니다.

![부하 테스트 시나리오](../test/media/loadtesteditinscenarios.png)

시나리오에는 다음 구성 요소가 포함됩니다.

|||
|-|-|
|용어|정의|
|브라우저 조합|가상 사용자가 다양한 웹 브라우저를 통해 웹 사이트에 액세스하는 것을 시뮬레이션합니다.|
|부하 패턴|부하 테스트 중에 활성인 가상 사용자 수와 새 사용자가 시작하는 속도를 지정합니다. 예를 들어 단계, 일정 및 목표 기반 패턴이 있습니다.|
|테스트 조합 모델|부하 테스트 시나리오에서 가상 사용자가 지정한 테스트를 실행할 확률을 지정합니다. 예를 들어 TestA를 실행할 확률 20%, TestB를 실행할 확률 80%로 지정합니다. 테스트 조합 모델에는 특정 시나리오에 대한 테스트의 목표가 반영되어야 합니다.|
|테스트 조합|테스트 조합은 시나리오를 구성하도록 선택한 웹 성능 및 단위 테스트와 이러한 테스트의 배포를 나타냅니다.|
|네트워크 조합|가상 사용자가 다양한 네트워크 연결을 사용하여 웹 사이트에 액세스하는 것을 시뮬레이션합니다. 네트워크 조합에서는 LAN, 케이블 모뎀, 기타 옵션 등을 비롯한 옵션을 제공합니다.|

시나리오에는 부하 테스트 편집기를 사용하여 편집할 수 있는 여러 다른 속성이 포함되어 있습니다. 자세한 내용은 [부하 테스트 시나리오 속성](../test/load-test-scenario-properties.md)을 참조하세요.

## <a name="tasks"></a>작업

|작업|관련 항목|
|-----------|-----------------------|
|**시나리오에 인위적인 상호 작용 일시 중지 추가:** 인지 시간을 사용하여 웹 사이트와의 상호 작용 간에 대기하게 되는 사람의 동작을 시뮬레이션할 수 있습니다. 인지 시간은 웹 성능 테스트의 요청 간이나 부하 테스트 시나리오의 테스트 반복 간에 발생합니다. 부하 테스트에서 인지 시간 사용은 보다 정확한 부하 시뮬레이션을 만드는 데 유용합니다.|-   [인지 시간을 편집하여 웹 사이트 사용자 상호 작용 지연 시뮬레이션](../test/edit-think-times-in-load-test-scenarios.md)|
|**시나리오에 필요한 가상 사용자 수 지정:** 부하 패턴 속성을 구성하여 부하 테스트 중에 시뮬레이션된 사용자 부하가 조정되는 방식을 지정할 수 있습니다. 일정 부하, 단계 부하 및 목표 기반 부하라는 세 가지 부하 패턴이 기본적으로 제공됩니다. 부하 패턴을 선택하고 부하 테스트 목표에 맞는 적절한 수준으로 속성을 조정합니다.|-   [모델 가상 사용자 동작에 대한 부하 패턴 편집](../test/edit-load-patterns-to-model-virtual-user-activities.md)|
|**시나리오에서 가상 사용자가 테스트를 실행할 확률 구성:** 테스트 조합을 사용하여 부하 테스트 시나리오에서 가상 사용자가 특정 테스트를 실행할 확률을 지정할 수 있습니다. 이렇게 하면 부하를 보다 사실적으로 시뮬레이션할 수 있습니다. 응용 프로그램에서 워크플로를 하나만 사용하는 대신 여러 워크플로를 사용하면 최종 사용자가 응용 프로그램과 상호 작용하는 방식을 보다 가깝게 테스트할 수 있습니다.|-   [텍스트 조합 모델 편집](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)|
|**부하 테스트 시나리오에 웹 성능 또는 단위 테스트 추가 또는 제거:** 시나리오의 부하 테스트에 웹 성능 또는 단위 테스트를 추가하거나 제거할 수 있습니다. 부하 테스트에는 하나 이상의 시나리오가 포함되며, 각 시나리오에는 하나 이상의 웹 성능 또는 단위 테스트가 포함됩니다.|-   [테스트 조합 편집](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**시나리오에 필요한 네트워크 조합 구성:** 네트워크 조합을 사용하여 부하 테스트 시나리오에서 네트워크 부하를 보다 사실적으로 시뮬레이션할 수 있습니다. 부하는 단일 네트워크 형식 대신 유형이 다른 여러 네트워크 형식 목록을 사용하여 생성됩니다. 이를 통해 최종 사용자가 응용 프로그램과 상호 작용하는 방식을 보다 가깝게 테스트할 수 있습니다. 네트워크 조합 모델에는 해당 시나리오의 목표가 반영되어야 합니다.|-   [Virtual Network 형식 지정](../test/specify-virtual-network-types-in-a-load-test-scenario.md)|
|**시나리오에 적합한 웹 브라우저 조합 선택:** 브라우저 조합을 사용하여 부하 테스트 시나리오에서 웹 부하를 보다 사실적으로 시뮬레이션할 수 있습니다. 이를 통해 브라우저 하나가 아니라 서로 유형이 다른 여러 브라우저를 사용하여 부하가 생성됩니다. 따라서 응용 프로그램과 함께 실제로 사용될 브라우저를 보다 정확하게 테스트할 수 있습니다.|-   [웹 브라우저 형식 지정](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**시나리오의 테스트 반복 설정 구성:** 부하 테스트 편집기 및 속성 창에서 부하 테스트 시나리오를 편집하여 테스트 반복 설정을 구성할 수 있습니다. 기본적으로 시나리오는 최대 테스트 반복 횟수 없이 설정됩니다. 필요할 경우 시나리오의 최대 반복 횟수와 반복 간 일시 중지 시간을 구성할 수 있습니다.|-   [시나리오에 대한 테스트 반복 구성](../test/configure-test-iterations-in-a-load-test-scenario.md)|
|**시나리오의 지연 설정 구성:** 부하 테스트 편집기 및 속성 창을 사용하여 부하 테스트 시나리오를 시작하기 전의 지연을 지정할 수 있습니다. **지연 시작 시간** 속성을 사용해야 하는 예로는 다른 시나리오가 사용하는 항목을 만들기 시작하는 시나리오가 필요한 경우를 들 수 있습니다. 항목을 사용하는 시나리오를 지연하여 항목을 만드는 시나리오에 일부 데이터를 만들 시간을 부여할 수 있습니다.|-   [시나리오 시작 시간 지연 구성](../test/configure-scenario-start-delays.md)|
|**부하 테스트 시나리오에 사용할 원격 컴퓨터 지정:** 부하 테스트를 만든 후 부하 테스트 시나리오의 속성을 편집하여 포함할 테스트 에이전트를 나타낼 수 있습니다. 자세한 내용은 [테스트 컨트롤러 및 테스트 에이전트](configure-test-agents-and-controllers-for-load-tests.md)를 참조하세요.|-   [방법: 사용할 테스트 에이전트 지정](../test/how-to-specify-test-agents-to-use-in-load-test-scenarios.md)|

## <a name="see-also"></a>참고 항목

- [부하 테스트 편집](../test/edit-load-tests.md)
- [부하 테스트 시나리오 속성](../test/load-test-scenario-properties.md)