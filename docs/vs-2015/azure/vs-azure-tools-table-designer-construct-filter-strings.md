---
title: 테이블 디자이너에 대 한 필터 문자열 생성 하기 | Microsoft Docs
description: 테이블 디자이너에 대 한 필터 문자열 생성
author: ghogen
manager: douge
assetId: a1a10ea1-687a-4ee1-a952-6b24c2fe1a22
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/18/2016
ms.author: ghogen
ms.openlocfilehash: ff8c3dd927e81b9e131242a9a6631a8297046a6e
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002873"
---
# <a name="constructing-filter-strings-for-the-table-designer"></a>테이블 디자이너에 대한 필터 문자열 생성
## <a name="overview"></a>개요
Visual Studio에 표시 되는 Azure 테이블에 데이터를 필터링 할 **테이블 디자이너**, 필터 문자열을 생성 하 여 필터 필드에 입력 합니다. 필터 문자열 구문은 WCF Data Services에서 정의 됩니다 및 SQL WHERE 절과 유사 하지만 HTTP 요청을 통해 Table service에 전송 됩니다. 합니다 **테이블 디자이너** 를 적절 한 인코딩을 처리 이므로 desired 속성 값을 필터링 하려면 필요한 이름만 입력 속성 이름, 비교 연산자, 조건 값 및 필요에 따라 부울 필터 필드에는 연산자입니다. 쿼리를 통해 테이블에 대 한 URL을 생성 하는 경우 처럼 $filter 쿼리 옵션을 포함 해야 합니다 [Storage 서비스 REST API 참조](http://go.microsoft.com/fwlink/p/?LinkId=400447)합니다.

WCF Data Services에 기반한 합니다 [개방형 데이터 프로토콜](http://go.microsoft.com/fwlink/p/?LinkId=214805) (OData). 필터 시스템 쿼리 옵션에 대 한 자세한 내용은 (**$filter**)를 참조 합니다 [OData URI 규칙 사양](http://go.microsoft.com/fwlink/p/?LinkId=214806)합니다.

## <a name="comparison-operators"></a>비교 연산자
다음의 논리 연산자는 모든 속성 유형에 대해 지원 됩니다.

| 논리 연산자 | 설명 | 필터 문자열의 예 |
| --- | --- | --- |
| eq |Equal |City eq '와' |
| gt |보다 큼 |가격 20 |
| ge |크거나 같음 |보다 크거나 같은 가격 10 |
| lt |보다 작음 |20 보다 적은 가격 |
| le |작거나 같음 |보다 적거나 같은 가격 100 |
| ne |같지 않음 |과 같지 않은 도시 'London' |
| 를 갖는 |그리고 |보다 적거나 같은 가격 200 및 3.5 |
| 또는 |또는 |보다 적거나 같은 가격 3.5 또는 200 |
| not |not |isAvailable 없습니다 |

필터 문자열을 생성할 때 다음 규칙은 중요 합니다.

* 속성 값을 비교 하는 논리 연산자를 사용 합니다. 속성에 동적 값을 비교할 수는 식의 한쪽은 상수 여야 합니다.
* 필터 문자열의 모든 부분은 대/소문자를 구분 하지 않습니다.
* 상수 값을 올바른 결과 반환할 필터의 순서에서 속성으로 동일한 데이터 형식 이어야 합니다. 지원 되는 속성 형식에 대 한 자세한 내용은 참조 하세요. [Table Service 데이터 모델 이해](http://go.microsoft.com/fwlink/p/?LinkId=400448)합니다.

## <a name="filtering-on-string-properties"></a>문자열 속성 필터링
문자열 속성으로 필터링 하는 경우 문자열 상수를 작은따옴표로 묶습니다.

다음 예제에 대 한 필터를 **PartitionKey** 하 고 **RowKey** 속성, 키가 아닌 추가 속성 필터 문자열에 추가할 수도 있습니다.

    PartitionKey eq 'Partition1' and RowKey eq '00001'

이 필요 하지 않지만 각 필터 식을 괄호로 묶을 수 있습니다.

    (PartitionKey eq 'Partition1') and (RowKey eq '00001')

Table service는 와일드 카드 쿼리를 지원 하지 않습니다 하는 지원 되지 않으므로 테이블 디자이너에서 하거나 note 합니다. 그러나 원하는 접두사에서 비교 연산자를 사용 하 여 일치 하는 접두사를 수행할 수 있습니다. 다음 예제에서는 'A' 문자로 시작 하는 LastName 속성을 사용 하 여 엔터티를 반환합니다.

    LastName ge 'A' and LastName lt 'B'

## <a name="filtering-on-numeric-properties"></a>숫자 속성 필터링
정수 또는 부동 소수점 숫자를 필터링 하려면 따옴표 없이 숫자를 지정 합니다.

이 예제에서는 값이 30 보다 큰 Age 속성을 사용 하 여 모든 엔터티를 반환 합니다.

    Age gt 30

이 예제에서는 해당 값이 100.25 보다 작거나 같은 AmountDue 속성을 사용 하 여 모든 엔터티를 반환 합니다.

    AmountDue le 100.25

## <a name="filtering-on-boolean-properties"></a>부울 속성 필터링
지정 하는 부울 값을 필터링 하려면 **true** 하거나 **false** 인용 부호 제외 합니다.

다음 예제에서는 모든 엔터티를 반환 IsActive 속성이 설정 되어 있는 **true**:

    IsActive eq true

이 필터 식은 논리 연산자 없이 작성할 수 있습니다. 다음 예제에서는 Table service는 모든 엔터티도 반환 IsActive가 **true**:

    IsActive

모든 엔터티 IsActive가 false를 반환 하려면 not을 사용할 수 있습니다 연산자:

    not IsActive

## <a name="filtering-on-datetime-properties"></a>DateTime 속성 필터링
날짜/시간 값을 필터링 하려면 지정 합니다 **날짜/시간** 키워드 뒤에 작은따옴표로 date/time 상수입니다. Date/time 상수는에 설명 된 대로 결합 된 UTC 형식에서 이어야 합니다 [DateTime 속성 값 서식 지정](http://go.microsoft.com/fwlink/p/?LinkId=400449)합니다.

다음 예제에서는 CustomerSince 속성이 2008 년 7 월 10 일인 경우 엔터티를 반환 합니다.

    CustomerSince eq datetime'2008-07-10T00:00:00Z'
