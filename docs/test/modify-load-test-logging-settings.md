---
title: 부하 테스트 로깅 설정
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging, modifying
ms.assetid: 9649226a-857d-41ef-8ec7-047b6e498033
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.openlocfilehash: 88819e8858a57a16e327e8e7b04f69c74fe5045a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900784"
---
# <a name="modify-load-test-logging-settings"></a>부하 테스트 로깅 설정 수정

완료된 부하 테스트의 결과에는 테스트 대상 컴퓨터에서 주기적으로 로그에 수집된 성능 카운터 샘플 및 오류 정보가 포함되어 있습니다. 부하 테스트 실행 과정에서 많은 수의 성능 카운터 샘플이 수집될 수 있습니다. 수집되는 성능 데이터의 양은 테스트 실행의 길이, 샘플링 간격, 테스트 대상 컴퓨터 수 및 수집되는 카운터의 수에 따라 달라집니다. 대규모 부하 테스트의 경우 수집되는 성능 데이터의 양이 몇 기가바이트가 되기 쉽습니다. 따라서 데이터가 로그에 저장되는 빈도를 수정해야 할 수 있습니다. [테스트 컨트롤러 및 테스트 에이전트](configure-test-agents-and-controllers-for-load-tests.md)를 참조하세요.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

*테스트 컨트롤러*에서는 테스트가 실행되는 동안 수집된 모든 부하 테스트 샘플 데이터를 데이터베이스 로그에 스풀링합니다. 타이밍 정보와 오류 정보 같은 추가 데이터는 테스트가 완료된 후에 데이터베이스로 로드됩니다.

|작업|관련 항목|
|-|-----------------------|
|**부하 테스트가 실패할 경우 로그 저장:** 부하 테스트가 실패할 때마다 테스트 로그를 저장할지 여부를 지정할 수 있습니다.|-   [방법: 테스트 실패를 테스트 로그에 저장할지 여부 지정](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|
|**로그 파일의 최대 파일 크기 설정:** 테스트 컨트롤러 서비스와 연결된 XML 구성 파일을 편집하여 로그 파일에 사용할 최대 파일 크기를 지정할 수 있습니다.|[방법: 로그 파일의 최대 크기 지정](../test/how-to-specify-the-maximum-size-for-the-log-file.md)|

## <a name="see-also"></a>참고 항목

- [부하 테스트 실행 설정 구성](../test/configure-load-test-run-settings.md)