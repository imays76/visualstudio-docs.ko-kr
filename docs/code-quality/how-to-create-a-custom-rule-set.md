---
title: Visual Studio에서 설정 하는 사용자 지정 코드 분석 규칙 만들기
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- Development Edition, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dce43c02f4976b51bab61a48f615fb0307102fc7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49884188"
---
# <a name="customize-a-rule-set"></a>규칙 집합을 사용자 지정

코드 분석을 위한 특정 프로젝트 요구 사항에 맞게 설정 사용자 지정 규칙을 만들 수 있습니다.

## <a name="create-a-custom-rule-set"></a>사용자 지정 규칙 집합 만들기

사용자 지정 규칙 집합을 만들려면, 기본 제공 규칙 집합에 열 수 있습니다 합니다 **규칙 집합 편집기**합니다. 여기에서 추가 하거나 특정 규칙을 제거할 수 있습니다 및 규칙이 위반 될 때 발생 하는 동작을 변경할 수 있습니다&mdash;예를 들어, 경고 또는 오류를 표시 합니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택한 **속성**합니다.

2. 에 **속성** 페이지를 선택 합니다 **코드 분석** 탭 합니다.

3. 에 **이 규칙 집합 실행** 드롭 다운 목록에서 다음 중 하나를 수행 합니다.

   - 사용자 지정 하려는 규칙 집합을 선택 합니다.

     \- 또는 -

   - 선택  **\<찾아보기... >** 목록에 없는 기존 규칙 집합을 지정 하려면.

4. 선택 **열고** 규칙 규칙 집합 편집기에 표시를 합니다.

새 규칙 집합 파일을 만들 수도 있습니다는 **새 파일** 대화 상자:

1. 선택 **파일** > **새로 만들기** > **파일**를 누르거나 **Ctrl**+**N**.

2. 에 **새 파일** 대화 상자를 선택 합니다 **일반** 왼쪽의 범주 선택한 후 **코드 분석 규칙 집합**.

3. **열기**를 선택합니다.

   새 *.ruleset* 파일이 규칙 집합 편집기에서 열립니다.

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>사용자 지정 규칙 집합에서 여러 규칙 집합

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택한 **속성**합니다.

2. 에 **속성** 페이지를 선택 합니다 **코드 분석** 탭 합니다.

3. 선택  **\<여러 규칙 집합 선택 >** 에서 **이 규칙 집합 실행**합니다.

4. 에 **추가 또는 제거할 규칙 집합** 대화 상자에서 규칙 집합 선택 하려면 새 규칙 집합에 포함 합니다.

   ![추가 또는 제거 규칙 집합 대화 상자](media/add-remove-rule-sets.png)

5. 선택 **다른 이름으로 저장**에 대 한 이름을 입력 합니다 *.ruleset* 파일을 선택한 후 **저장**합니다.

   새 규칙 집합을 선택 합니다 **이 규칙 집합 실행** 목록입니다.

6. 선택 **엽니다** 를 규칙 집합 편집기에서 설정 하 고 새 규칙을 엽니다.

## <a name="name-and-description"></a>이름 및 설명

편집기에서 열려 있는 규칙 집합의 표시 이름을 변경 하려면 합니다 **속성** 를 선택 하 여 창 **뷰** > **속성 창** 메뉴 모음에서. 표시 이름을 입력 합니다 **이름을** 상자입니다. 또한 규칙 집합에 대 한 설명을 입력할 수 있습니다.

## <a name="next-steps"></a>다음 단계

규칙 집합을 설정 했으므로 다음 단계를 추가 하거나 규칙을 제거 하거나 규칙 위반의 심각도 수정 하 여 규칙을 사용자 지정할 경우

> [!div class="nextstepaction"]
> [규칙 집합 편집기에서 규칙 수정](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>참고자료

- [방법: 관리 코드 프로젝트에 대한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [코드 분석 규칙 집합 참조](../code-quality/rule-set-reference.md)