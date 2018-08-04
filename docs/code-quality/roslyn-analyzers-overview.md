---
title: Visual Studio에서 Roslyn 분석기
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3d5836c0522ef97a634f44799934aab2750b3a45
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39511424"
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>.NET 컴파일러 플랫폼 분석기 개요

Visual Studio 2017에 입력할 때 C# 또는 Visual Basic 코드를 분석 하는.NET 컴파일러 플랫폼 분석기의 기본 제공 집합을 포함 합니다. NuGet 패키지로 추가 분석기-프로젝트별으로 또는 Visual Studio 확장으로 설치할 수 있습니다. 분석기 코드 스타일, 코드 품질 및 유지 관리, 코드 디자인 및 기타 문제를 살펴봅니다.

보고 되는 분석기 규칙 위반 발견 되 면으로 코드 편집기에 모두를 *구불구불한* 문제를 일으키는 코드 아래 및 합니다 **오류 목록**.

여러 분석기 규칙 또는 *진단을*, 하나 이상의 연결 된 *코드 수정을* 문제를 해결 하려면 적용할 수 있습니다. Visual Studio에 기본 제공 되는 분석기 진단 관련된 코드 픽스를 경우 코드 수정 전구 아이콘 메뉴의 다른 형식과 함께 표시 됩니다 *빠른 작업*합니다. 이러한 코드 수정에 대 한 정보를 참조 하세요 [일반적인 빠른 작업](../ide/common-quick-actions.md)합니다.

![분석기 위반 및 빠른 작업 코드 수정](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>정적 코드 분석 및 Roslyn 분석기

.NET 컴파일러 플랫폼 ("Roslyn") 분석기는 대체 [정적 코드 분석](../code-quality/code-analysis-for-managed-code-overview.md) 관리 코드에 대 한 합니다. Roslyn 분석기 진단으로 다시 작성 되었습니다 이미 다양 한 정적 코드 분석 규칙.

정적 코드 분석 규칙 위반을 같은 Roslyn 분석기 위반에 표시 된 **오류 목록**합니다. 또한 Roslyn 분석기 위반에에서도 표시로 코드 편집기 *물결 모양* 문제를 일으키는 코드 아래. 구불구불한는 색에 따라 달라 집니다 합니다 [심각도 설정](../code-quality/use-roslyn-analyzers.md#rule-severity) 규칙의 합니다. 다음 스크린샷은 3 위반&mdash;빨간색 하나, 녹색 하나 및 하나 회색:

![코드 편집기에서 물결 모양](media/diagnostics-severity-colors.png)

정적 코드 분석을 사용 하는 경우 또한 입력할 때 live와 같은 빌드 시 코드를 분석 하는 Roslyn 분석기! Roslyn 분석기 사용 하도록 설정 하면 편집기에에서 열려 있는 없는 코드 파일의 디자인 타임에 분석을 제공할 수도 있습니다 [전체 솔루션 분석](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis)합니다.

> [!NOTE]
> Roslyn 분석기에서 빌드 시간 오류 및 경고는 표시만 경우 분석기는 NuGet 패키지로 설치 됩니다.

Roslyn 분석기는 동일한 유형의 정적 코드 분석을 수행 하는 문제를 보고 하지 할 뿐만 아니라 쉽게 하나 또는 모두를 파일 또는 프로젝트에 위반 횟수를 수정할 수 있도록 합니다. 이러한 작업 이라고 *코드 수정을*합니다. 코드 수정 IDE로 적용 됩니다. Visual Studio에서으로 구현 된 사실을 [빠른 작업](../ide/quick-actions.md)합니다. 일부 분석기 진단 관련된 코드 픽스를 경우

> [!NOTE]
> 메뉴 옵션을 **분석** > **코드 분석 실행** 만 정적 코드 분석을 적용 합니다. 프로젝트의에서 뿐만 **코드 분석** 속성 페이지의 **빌드에 코드 분석 사용** 및 **생성 된 코드 결과 표시 안 함** 확인란에만 적용 정적 코드 분석 합니다. Roslyn 분석기에서 효과가 없습니다.

Roslyn 분석기에서 위반 및의 정적 코드 분석을 구분 하는 **오류 목록**를 확인 합니다 **도구** 열. 도구 값 분석기 어셈블리 중 하 나와 일치 하는 경우 **솔루션 탐색기**예를 들어 **Microsoft.CodeQuality.Analyzers**, 위반 Roslyn 분석기에서 제공 됩니다. 그렇지 않으면 위반 정적 코드 분석에서 시작 됩니다.

![오류 목록에 열 도구](media/code-analysis-tool-in-error-list.png)

## <a name="nuget-package-versus-vsix-extension"></a>VSIX 확장 및 NuGet 패키지

Visual Studio 확장으로 NuGet 패키지 또는 전체 Visual Studio를 통해 프로젝트를 설치 하는.NET 컴파일러 플랫폼 분석기 될 수 있습니다. 몇 가지 핵심 동작 차이점이의이 두 메서드 간의 [분석기 설치](../code-quality/install-roslyn-analyzers.md)합니다.

### <a name="scope"></a>범위

Visual Studio 확장으로 분석기를 설치 하는 경우 적용할 솔루션 수준에서 Visual Studio의 모든 인스턴스입니다. 분석기는 것이 좋습니다, NuGet 패키지를 설치 하는 경우 NuGet 패키지가 설치 된 프로젝트에만 적용 됩니다. 팀 환경에서 NuGet 패키지로 설치 하는 분석기 범위에 있는 *모든 개발자가* 는 해당 프로젝트에서 작동 합니다.

### <a name="build-errors"></a>빌드 오류

(CI) 빌드 명령줄을 통해 또는 지속적인 통합의 일부로 포함 하는 빌드 타임에 적용 하는 규칙에 분석기를 NuGet 패키지로 설치 합니다. 분석기 경고 및 오류 나타나지 빌드 보고서에 확장으로 분석기를 설치 하는 경우.

다음 스크린샷에서 분석기 규칙 위반을 포함 하는 프로젝트 개발에 이르기까지 명령줄 빌드 출력을 보여 줍니다.

![규칙 위반을 사용 하 여 MSBuild 출력](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>규칙 심각도

Visual Studio 확장으로 설치 된 분석기에서 규칙의 심각도 설정할 수 없습니다. 구성 하려면 [규칙 심각도](../code-quality/use-roslyn-analyzers.md#rule-severity), 분석기를 NuGet 패키지로 설치 합니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [Visual Studio에서 Roslyn 분석기 설치](../code-quality/install-roslyn-analyzers.md)

> [!div class="nextstepaction"]
> [Visual Studio에서 Roslyn 분석기 사용](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>참고자료

- [Visual Studio에서 빠른 작업](../ide/quick-actions.md)
- [사용자 고유의 Roslyn 분석기 작성](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET compiler Platform SDK](/dotnet/csharp/roslyn-sdk/)