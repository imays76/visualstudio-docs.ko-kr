---
title: C/C++용 코드 분석 개요
ms.date: 04/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 35f694d9cc397800249dd9b4acd86bf63d22ad93
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44320711"
---
# <a name="code-analysis-for-cc-overview"></a>C/c + + 개요에 대 한 코드 분석

C/c + + 코드 분석 도구는 C/c + + 소스 코드에서 발생할 수 있는 오류에 대 한 정보를 제공합니다. 이 도구를 통해 보고되는 일반적인 코딩 오류에는 버퍼 오버런, 초기화되지 않은 메모리, null 포인터 역참조, 메모리 및 리소스 누수 등이 포함됩니다. 도구에 대 한 검사를 실행할 수도 있습니다는 [c + + Core Guidelines](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)합니다.

## <a name="ide-integrated-development-environment-integration"></a>IDE (통합된 개발 환경) 통합

코드 분석 도구는 Visual Studio IDE 내에서 완벽 하 게 통합 되어 있습니다.

빌드 프로세스 중 소스 코드에 대해 생성 된 모든 경고가 오류 목록에 표시 됩니다. 경고를 발생 시킨 소스 코드를 이동할 수 있습니다 및 해당 원인 및 문제 해결에 대 한 추가 정보를 볼 수 있습니다.

## <a name="command-line-support"></a>명령줄 지원

또한 다음 예와에서 같이 명령줄에서 분석 도구를 사용할 수 있습니다.

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 버전 15.7 이상의** CMake를 비롯 한 모든 빌드 시스템을 사용 하 여 명령줄에서 도구를 실행할 수 있습니다.

## <a name="pragma-support"></a>#pragma 지원

사용할 수는 `#pragma` 지시문으로 경고를 오류로 처리를 사용 하도록 설정 또는 경고를 사용 하지 않도록 설정 하 고 개별 코드 줄에 대 한 경고 표시 안 함. 자세한 내용은 [방법: C/c + + 프로젝트에 대 한 코드 분석 속성 설정](how-to-set-code-analysis-properties-for-c-cpp-projects.md)합니다.

## <a name="annotation-support"></a>주석 지원

주석을 코드 분석의 정확성을 개선 합니다. 주석이 함수 매개 변수에서 사전 및 사후 조건에 대 한 추가 정보를 제공 및 반환 형식입니다. 자세한 내용은 참조 하세요. [방법: __analysis_assume를 사용 하 여 추가 코드 정보 지정](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>체크 인 정책의 일부로 분석 도구를 실행 합니다.

모든 소스 코드 체크 인 특정 정책을 충족 필요할 수도 있습니다. 특히, 최신 로컬 빌드 단계로 분석을 실행 하는지 확인 하려고 합니다. 코드 분석 체크 인 정책을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [만들기 및 사용 하 여 코드 분석 체크 인 정책](../code-quality/creating-and-using-code-analysis-check-in-policies.md)

## <a name="team-build-integration"></a>팀 빌드 통합

단계로 코드 분석 도구를 실행 하려면 빌드 시스템의 통합된 된 기능을 사용할 수는 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 빌드 프로세스입니다. 자세한 내용은 [Azure 파이프라인](/azure/devops/pipelines/index?view=vsts)합니다.

## <a name="see-also"></a>참고자료

- [C/c + +에 대 한 빠른 시작: 코드 분석](quick-start-code-analysis-for-c-cpp.md)
- [연습: C/c + + 코드 오류 분석](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [C/C++용 코드 분석 경고](code-analysis-for-c-cpp-warnings.md)
- [C++ Core Guidelines 검사기 사용](using-the-cpp-core-guidelines-checkers.md)
- [C + + 핵심 지침 검사기 참조](code-analysis-for-cpp-corecheck.md)
- [규칙 집합을 사용하여 실행할 C++ 규칙 지정](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [코드 분석 도구를 사용 하 여 드라이버 품질 분석](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [드라이버 경고에 대 한 코드 분석](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
