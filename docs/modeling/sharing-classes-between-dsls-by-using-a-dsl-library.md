---
title: DSL 라이브러리를 사용하여 DSL 간에 클래스 공유
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: f95cc7fad1b4aaac3da687352cf5561a7d72ff8e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53897841"
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>DSL 라이브러리를 사용하여 DSL 간에 클래스 공유
Visual Studio Visualization and Modeling SDK를에 다른 DSL에 가져올 수 있는 불완전 한 DSL 정의 만들 수 있습니다. 이렇게 하면 유사한 모델의 공통 부분을 구분할 수 있습니다.

## <a name="creating-and-using-dsl-libraries"></a>만들기 및 DSL 라이브러리를 사용 합니다.

#### <a name="to-create-a-dsl-library"></a>DSL 라이브러리를 만들려면

1.  새 DSL 프로젝트를 만들고 DSL 라이브러리 솔루션 템플릿을 선택 합니다.

     빈 모델을 사용 하 여 단일 DSL 프로젝트 만들어질 수 있습니다.

2.  도메인 클래스, 관계, 셰이프 등 추가할 수 있습니다.

     라이브러리에 있는 요소는 단일 포함 트리를 형성 필요가 없습니다.

     가져오기를 사용할 수 있는 관계를 정의 하려면 두 도메인 클래스와의 관계를 만듭니다.

     설정을 고려 합니다 **상속 한정자** 도메인 클래스의 `Abstract`합니다.

3.  연결 작성기와 같은 DSL 탐색기에서 정의 하는 요소를 추가할 수 있습니다.

4.  유효성 검사 제약 조건 등의 추가 코드를 필요로 하는 사용자 지정 항목을 추가할 수 있습니다.

5.  클릭 **모든 템플릿 변환**합니다.

6.  프로젝트를 빌드합니다.

7.  컴파일된 어셈블리 (DLL) 및 파일을 모두 제공 해야 다른 사람들이 사용 하 여 DSL을 배포할 때 `DslDefinition.dsl`합니다. 아래에 폴더에서 컴파일된 어셈블리를 찾을 수 있습니다. `Dsl\bin\*`

#### <a name="to-import-a-dsl-library"></a>DSL 라이브러리를 가져오려면

1. 다른 DSL 정의에서 **DSL 탐색기**에서 DSL의 루트 클래스를 마우스 오른쪽 단추로 클릭 하 고 클릭 **새 DslLibrary 가져오기 추가**합니다.

2. 속성 창에서 설정 된 **파일 경로** 라이브러리입니다. 상대 경로 또는 절대 경로 사용할 수 있습니다.

    가져온된 라이브러리는 읽기 전용 모드에서 DSL 탐색기에 나타납니다.

3. 가져온된 클래스를 기본 클래스로 사용할 수 있습니다. 가져오기 DSL에서 도메인 클래스를 만들고 속성 창의 설정 **기본 클래스** 가져온 클래스입니다.

4. 모든 템플릿 변환 하는 클릭 합니다.

5. DSL 라이브러리 프로젝트에서 빌드된 어셈블리 (DLL)에 대 한 참조를 DSL 프로젝트에 추가 합니다.

6. 솔루션을 빌드합니다.

   DSL 라이브러리는 다른 라이브러리를 가져올 수 있습니다. 라이브러리를 가져올 때 해당 import도 자동으로 DSL 탐색기에 나타납니다.

## <a name="see-also"></a>참고 항목

- [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
