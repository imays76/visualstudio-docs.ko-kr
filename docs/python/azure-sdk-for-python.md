---
title: Python용 Azure SDK
description: Python용 Azure SDK를 사용하면 모든 플랫폼에서 실행되는 Python 응용 프로그램을 통해 Microsoft Azure 서비스를 쉽게 이용할 수 있습니다.
ms.date: 10/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: b1b41fe707c751b5cd32706d1c27f707f964dff8
ms.sourcegitcommit: 40b6438b5acd7e59337a382c39ec711b9e99cc8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49100928"
---
# <a name="azure-sdk-for-python"></a>Python용 Azure SDK

Python용 Azure SDK를 사용하면 Windows, MacOS 및 Linux에서 실행되는 응용 프로그램에서 Microsoft Azure 서비스를 쉽게 사용하고 관리할 수 있습니다.

## <a name="installation"></a>설치

Azure SDK는 [Python 패키지 인덱스](https://pypi.python.org/pypi/azure)에서 설치됩니다.

다음과 같이 **안정적인 최신 버전**(Python 2.7 및 3.x 지원)을 설치합니다.

```command
pip install azure
```

또한 Azure 설명서에서 [Python 및 SDK 설치](https://docs.microsoft.com/azure/python-how-to-install/)를 수행할 수도 있습니다.

## <a name="documentation"></a>설명서

[Python용 Azure SDK 개발자 센터](https://docs.microsoft.com/python/azure/?view=azure-python)에는 다음과 같은 여러 가지 자습서를 포함하여 유용한 리소스도 많이 있습니다.

- Linux의 Azure App Service에서 웹앱 만들기(/azure/app-service/containers/quickstart-python)
- [Blob 저장소](/azure/storage/blobs/storage-quickstart-blobs-python)
- [테이블 저장소](/azure/cosmos-db/table-storage-how-to-use-python)
- [큐 저장소](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [Service Bus 큐](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Service Bus 토픽/구독](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [서비스 관리](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

설명서가 없는 공용 API의 경우 [SDK GitHub 리포지토리](https://github.com/Azure/azure-sdk-for-python)에 있는 단위 테스트가 좋은 정보 자료가 됩니다.

- [저장소 단위 테스트](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Service Bus 단위 테스트](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [서비스 관리 단위 테스트](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>Support(지원)

SDK에 대한 GitHub 리포지토리는 [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python)에 있습니다.

문제를 발견하거나 SDK 사용에 대한 질문이 있는 경우 [리포지토리에 문제를 보고](https://github.com/Azure/azure-sdk-for-python/issues)해 주세요.
