---
title: IntelliCode 질문 및 답변
ms.date: 07/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
ms.openlocfilehash: 79e18778eae231d16cf32c0fa68bcb6f5564b09d
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39079313"
---
# Visual Studio IntelliCode FAQ

Visual Studio IntelliCode에 관심을 가져 주셔서 감사합니다. 이 간단한 FAQ를 통해 귀하가 궁금해 할 만한 몇 가지 사항에 해답이 되기를 바랍니다.

## 질문. Visual Studio IntelliCode란 무엇인가요?

Microsoft는 빌드 2018에서 AI를 사용하여 소프트웨어 개발을 개선하는 새로운 기능인 Visual Studio IntelliCode를 도입했습니다. IntelliCode는 개발자와 팀이 자신 있게 코딩하고, 더 빠르게 문제를 찾고, 코드 검토에 집중하는 데 도움을 줍니다.

다음과 같은 방법으로 IntelliCode가 소프트웨어 개발 프로세스를 개선하는 방법의 초기 모습을 보여주었습니다.

- 컨텍스트 인식 코드 완성본 제공
- 개발자에게 팀의 패턴 및 스타일을 준수하도록 안내
- 찾기 어려운 코드 문제 발견
- 정말 중요한 영역으로 주의를 끌어 코드 검토에 집중

개발자는 [https://aka.ms/intellicode](https://aka.ms/intellicode)에서 자세한 정보를 찾고 새로운 소식 및 향후 비공개 미리 보기를 위해 등록할 수 있습니다.

## 질문. 고객은 Visual Studio IntelliCode로 무엇을 할 수 있나요?

Visual Studio IntelliCode는 AI(인공 지능)를 통해 새로운 생산성 향상 기능을 제공하는 광범위한 기능입니다.

개발자는 Visual Studio 2017 버전 15.7 이상을 위한 [실험적 확장을 다운로드](https://go.microsoft.com/fwlink/?linkid=872707)할 수 있습니다. 현재 확장에서는 다음을 제공합니다.

- 멤버에 대한 사전순 목록만 제공하지 않고 개발자가 사용하기에 가장 적합한 API를 예측하는 AI 향상된 IntelliSense를 제공합니다. 개발자의 현재 코드 컨텍스트 및 패턴을 사용하여 이 동적 목록을 제공합니다.

- 코드 스타일 및 서식 지정 규칙의 유추를 통해 코딩 스타일 및 서식을 정의하는 코드베이스의 [.editorconfig 파일](../create-portable-custom-editor-options.md)을 동적으로 만들어서 코드의 일관성을 유지할 수 있습니다. 이러한 규칙을 사용하면 Visual Studio에서 자동으로 스타일 및 서식을 수정하여 문서를 정리할 수 있습니다.

몇 달 내로 확장에 추가 기능을 업데이트할 예정입니다.

## 질문. EditorConfig 유추가 파일 이름에 1을 추가하는 이유는 무엇인가요?

Visual Studio 확장성의 알려진 문제가 1을 발생시켜서 **추가 > 새 항목**을 마우스 오른쪽 단추로 클릭하고 선택하여 만들 때 .editorconfig 파일 이름에 추가됩니다. 이 방식으로 명명된 파일은 Visual Studio에서 editorconfig 프로세서에 의해 인식되지 않습니다. 이 문제는 Visual Studio 2017 15.8 미리 보기 4 버전에서 해결되었지만 그 때까지는 **새 항목 추가** 대화 상자에서 1을 제거하여 해결할 수 있습니다.

## 질문. 내 EditorConfig 규칙이 적용된다고 표시되지 않습니다. 이유는 무엇인가요?
이 문제가 발생하는 일반적인 이유 중 몇 가지는 다음과 같습니다.

- Visual Studio 2017 15.8 미리 보기 3 이전 버전에서 열려 있는 모든 문서를 닫고 다시 열어서 EditorConfig 파일의 규칙이 적용되는지 확인합니다. 이 문제는 15.8 미리 보기 3 릴리스에서 해결되었습니다.
- 서식 지정 규칙은 **오류 목록**에서 표시되지 않거나 코드에서 "오류 표시선"으로 표시되지 않습니다. 그러나 Visual Studio 2017 15.8 미리 보기 3 버전 이상에서 새 서식 문서(Ctrl+K, Ctrl+D) 확장을 사용하여 해결할 수 있습니다.

## 질문. 서식 문서가 내 스타일 규칙을 수정하지 않습니다. 이유는 무엇인가요?
이 문제가 발생하는 일반적인 이유 중 몇 가지는 다음과 같습니다.

- Visual Studio 2017 버전 15.8 미리 보기 3 이상을 사용하지 않고 있습니다. 이 버전이 확장된 "서식 문서" 명령을 사용하여 현재 문서에 대한 추가 코드 정리를 수행할 수 있어야 합니다.
- 스타일 수정에 옵트인되지 않을 수 있습니다. 서식 문서에서 규칙 기반 문제 기능을 수정하는 확장된 기능은 고정된 집합의 문제에 대해서만 다룹니다. **텍스트 편집기 > C# > 코드 스타일 > 서식 지정 > 일반 > 서식 문서 설정(실험)** 아래의 **도구 옵션**에서 해결된 문제를 변경할 수 있습니다. 기본 설정은 일부 스타일 규칙을 수정하지 않습니다. **도구 > 옵션**을 통해 이러한 설정을 선택할 수 있습니다. 예를 들어 "암시적/명시적 형식 기본 설정 적용"은 `var`을 사용하는 스타일 규칙을 실행합니다.

## 질문. Visual Studio IntelliCode에서 유추할 수 있는 EditorConfig 규칙은 무엇인가요?

현재 이 기능은 실험적이므로 [코드 스타일 설정 기본 설정](../editorconfig-code-style-settings-reference.md)에 설명된 전체 규칙 집합이 지원되지 않습니다.

IntelliCode는 현재 다음과 같은 규칙을 유추할 수 있습니다.

서식 지정 규칙:

-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_method_declaration_empty_parameter_list_parentheses
-   csharp_space_between_method_call_name_and_opening_parenthesis
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_call_empty_parameter_list_parentheses
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_parentheses
-   csharp_space_after_cast
-   csharp_space_after_colon_in_inheritance_clause
-   csharp_space_before_colon_in_inheritance_clause
-   csharp_space_around_binary_operators
-   csharp_indent_switch_labels
-   csharp_indent_case_contents
-   csharp_indent_case_contents_when_block
-   csharp_indent_labels
-   csharp_preserve_single_line_blocks
-   csharp_preserve_single_line_statements
-   csharp_new_line_before_open_brace
-   csharp_new_line_before_else
-   csharp_new_line_before_catch
-   csharp_new_line_before_finally
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_between_query_expression_clauses

스타일 규칙
-   csharp__new_line_before_catch
-   csharp_new_line_before_else
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_finally_style
-   csharp_new_line_between_query_expression_clauses
-   csharp_prefer_braces_style
-   csharp_preferred_modifier_order_style
-   csharp_prefer_simple_default_expression
-   csharp_preserve_single_line_blocks
-   csharp_space_after_cast
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_parentheses
-   csharp_style_expression_bodied_accessors
-   csharp_style_expression_bodied_constructors
-   csharp_style_expression_bodied_indexers
-   csharp_style_expression_bodied_methods
-   csharp_style_expression_bodied_operators
-   csharp_style_expression_bodied_properties
-   csharp_style_inlined_variable_declaration
-   csharp_style_pattern_local_over_anonymous_function
-   csharp_style_pattern_matching_over_as_with_null_check
-   csharp_style_var_for_built_in_types
-   csharp_style_var_when_type_is_apparent
-   dotnet_sort_system_directives_first
-   dotnet_style_explicit_tuple_names
-   dotnet_style_object_initializer
-   dotnet_style_predefined_type_for_locals_parameters_members
-   dotnet_style_predefined_type_for_member_access
-   dotnet_style_prefer_inferred_anonymous_type_member_names
-   dotnet_style_qualification_for_event
-   dotnet_style_qualification_for_field
-   dotnet_style_qualification_for_method
-   dotnet_style_qualification_for_property
-   dotnet_style_require_accessibility_modifiers

## 질문. Visual Studio IntelliCode 확장에 추가될 예정인 다른 기능이 있습니까?

다양한 기능을 열심히 개발하는 중이며 출시할 수 있게 되면 공개적으로 공유할 예정입니다. [https://aka.ms/intellicode](https://aka.ms/intellicode)에서 가입하여 뉴스 및 업데이트를 받아보면 새로운 기능이 언제 출시되는지 가장 먼저 알 수 있습니다.

## Q: IntelliCode에서 제공하는 “AI 지원 IntelliSense”가 일반 IntelliSense보다 나은 이유는 무엇인가요?

IntelliCode의 완성 목록은 단순한 사전순 멤버 목록을 제공하는 것이 아니라 개발자가 사용하기에 가장 적합한 API를 제안합니다. 개발자의 현재 코드 컨텍스트와 각각 100개 이상의 별점이 달린 GitHub의 고품질 오픈 소스 프로젝트 2000개에 기반을 둔 패턴을 사용하여 이러한 동적 목록을 제공합니다. 그 결과 가능성과 관련성이 가장 높은 API 호출을 예측하는 모델이 형성됩니다.

## Q: IntelliCode 완성 제안 기능은 얼마나 유용한가요?

Microsoft 내부에서 IntelliCode의 추천 기능을 얼마 동안 사용해 보았는데 유용한 제안 기능인 것 같습니다. 하지만 결국 직접 코딩할 때 이러한 추천 기능이 얼마나 유용한지 알 수 있을 것입니다. Visual Studio [IntelliCode 확장](https://go.microsoft.com/fwlink/?linkid=872707)을 한번 사용해 보시기 바랍니다. 얼마나 유용했는지 알려주시고, 피드백을 보내주세요. 또한 여러분이 추천 기능 중에서 선택한 항목에 따라 모델을 학습시켜 모델을 개선하면서 확장을 업데이트할 것입니다.

> [!NOTE]
> 사용자 정의 코드는 수집되지 않습니다. [개인 정보 보호](#privacy)에 대한 질문을 참조하세요.

## 질문. IntelliCode는 미래에 어떻게 되나요?

AI 및 기타 고급 기술을 사용하여 개발자의 생산성을 개선하기 위한 다양한 방법을 연구하는 중입니다. Microsoft 빌드 2018에서는 AI가 개발자에게 도움이 될 만한 몇 가지 시나리오의 초기 모습을 보여 주었지만 그 밖에도 많이 있습니다. 지금까지 당사에서 보여 드린 기능을 가지고 실험하는 개발자 분들의 의견을 듣고 싶습니다. [https://aka.ms/intellicode](https://aka.ms/intellicode)에서 가입하여 뉴스 및 업데이트를 받아보세요.

## 질문. 가격은 얼마인가요?

현재 가격 책정과 관련한 공지 사항은 없습니다.

## 질문. IntelliCode는 언제 출시되나요?

IntelliCode의 AI 지원 IntelliSense는 현재 첫 번째 실험적 미리 보기 상태입니다. 실험적 확장을 계속 업데이트하고, 향후 기능을 추가할 예정입니다. 최종 릴리스 날짜는 아직 미정이지만 최상의 경험을 제공하기 위해 개발자 여러분들의 피드백을 기다립니다. [https://aka.ms/intellicode](https://aka.ms/intellicode)에서 가입하여 뉴스 및 업데이트를 받아볼 수 있습니다.

## 질문. 이 환경은 Visual Studio 및 C#에서만 사용할 수 있나요?

이 환경은 C# 코드베이스의 Visual Studio 2017 빌드 2018에 도입되었습니다. 하지만 향후 Visual Studio 제품군의 더 많은 언어와 도구로 IntelliCode를 확장할 예정입니다.

## 질문. <a name="whynointellisense"/> C# 편집 환경에서 IntelliCode 제안을 볼 수 없습니다. 이유가 무엇입니까?

IntelliCode 제안은 C#의 표준 Visual Studio IntelliSense UI에 나타납니다. 해당 UI를 재정의하는 확장은 IntelliCode "별 모양" 제안이 목록 맨 위에 나타나지 않도록 방지합니다. 이 기능을 해제한 다음, IntelliSense를 다시 실행하여 확장이 이 동작을 유발하는지 확인할 수 있습니다.

이렇게 해도 문제가 해결되지 않으면 Visual Studio [문제 보고](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) 기능을 통해 문제를 보고하고 보고서에 IntelliCode를 언급합니다.

## 질문. 이 확장을 실행하는 데 필요한 Visual Studio 릴리스는 무엇인가요?

Visual Studio IntelliCode 확장은 Visual Studio 2017 버전 15.7 미리 보기 5 이상(모든 SKU)에서 지원됩니다. 필요한 최소 버전이 설치되지 않은 경우 "이 확장은 현재 설치되어 있는 제품에 설치할 수 없습니다."와 함께 확장 설치가 중단됩니다.

## 질문. 이 환경은 영어로만 지원되나요?

IntelliCode는 현재 미리 보기 확장이며, Microsoft에서는 이러한 기능이 광범위한 고객에게 얼마나 유용한지 파악하고자 합니다. IntelliCode 미리 보기가 종료되면 여러분의 피드백에 따라 우선적으로 지원할 로캘이나 언어, 패키징 방법을 확실히 고려할 것입니다.

## <a name="privacy"/> Q: 개인 정보 보호는 어떤가요? 제 코드가 클라우드로 전송되나요? 어떤 고객 데이터가 Microsoft로 전송되나요?

개발자 여러분, 지금 바로 실험적 미리 보기 확장인 Visual Studio IntelliCode를 사용해 보시기 바랍니다. 이 확장의 목적은 개발자 여러분들이 IntelliCode의 기능을 테스트하고 제품 팀에 의견을 제공하도록 하는 것입니다.

제품 개선을 위해 확장에서 익명화된 사용 및 오류 보고 데이터 중 일부가 수집됩니다. 사용자 정의 코드는 Microsoft로 전송되지 않지만 IntelliCode 결과 사용에 대한 정보는 수집됩니다. 이 데이터에는 오픈 소스 및 .NET 형식과 개발자가 IntelliCode의 제안 목록에서 선택한 멤버만 포함됩니다. 개발자는 [Visual Studio 환경 개선 프로그램](../../ide/visual-studio-experience-improvement-program.md)을 옵트아웃(opt out)할 수 있으며, 그러면 IntelliCode 확장에 대한 데이터 수집도 해제됩니다. 메뉴 표시줄에서 **도움말** > **의견 보내기** > **설정**을 선택합니다. **Visual Studio 환경 개선 프로그램** 대화 상자에서 **아니요, 참여하지 않겠습니다**를 선택한 후 **확인**을 선택합니다.

IntelliCode 확장은 정기적으로 개발자에게 설문 조사를 완료하도록 요청할 수 있습니다. 다시 말하지만 이 설문 조사는 익명으로 처리됩니다. 사용자는 가입하여 뉴스 및 이후 비공개 미리 보기를 받아볼 수 있지만 현재 실험적 확장을 사용할 때는 그렇게 하지 않아도 됩니다.

향후 기능에서는 가입이 필요한 서비스에 대한 액세스 권한을 요청할 수 있습니다. 이러한 기능의 비공개 미리 보기가 준비되면 자세한 내용을 알려드리겠습니다.
