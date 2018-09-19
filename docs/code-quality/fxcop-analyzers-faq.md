---
title: FxCop 코드 분석 및 FxCop 분석기
ms.date: 09/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- code analysis FAQ
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e05dd0e01254bf1222a8a7de497b11ec2a808bfb
ms.sourcegitcommit: b9a32c3d94b19e7344f4872bc026efd3157cf220
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46136369"
---
# <a name="frequently-asked-questions-about-fxcop-and-fxcop-analyzers"></a>FxCop 및 FxCop에 대 한 질문과 대답 분석기

레거시 FxCop 및 FxCop 간의 차이점을 이해 하려면 약간 어려울 수 있습니다 분석기입니다. 이 문서는 질문이 있는 경우 중 일부를 해결 하려고 합니다.

## <a name="whats-the-difference-between-legacy-fxcop-and-fxcop-analyzers"></a>레거시 FxCop 및 FxCop 차이점은 무엇 분석기?

레거시 FxCop 컴파일된 어셈블리에서 빌드 후 분석을 실행 합니다. 라는 별도 실행 파일로 실행 **FxCopCmd.exe**합니다. FxCopCmd.exe 컴파일된 어셈블리를 로드 합니다. 코드 분석을 실행 하 고 다음 결과 보고 (또는 *진단*).

FxCop 분석기는.NET 컴파일러 플랫폼 ("Roslyn")를 기반으로 합니다. 있습니다 [NuGet 패키지로 설치](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-nuget-package) 프로젝트 또는 솔루션에서 참조 되는 합니다. 소스 코드를 실행 하는 FxCop 분석기 기반 컴파일러 실행 하는 동안 분석 합니다. 하거나 컴파일러 프로세스 내에서 호스팅되는 FxCop 분석기 **csc.exe** 또는 **vbc.exe**, 프로젝트를 빌드할 때 분석을 실행 합니다. 분석기 결과 컴파일러 결과 함께 보고 됩니다.

> [!NOTE]
> 할 수도 있습니다 [FxCop 분석기는 Visual Studio 확장 설치](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-vsix)합니다. 이 경우 분석기 실행 코드 편집기에 입력 하지만 빌드 시간에 실행 하지 않습니다. CI (지속적인 통합)의 일부로 FxCop 분석기를 실행 하려는 경우 설치 NuGet 패키지로 대신 합니다.

## <a name="does-the-run-code-analysis-command-run-fxcop-analyzers"></a>코드 분석 실행 명령을 FxCop 분석기를 실행 하나요?

아니요. 선택 하면 **분석** > **코드 분석 실행** Visual Studio 2017에서이 정적 코드 분석 또는 레거시 FxCop을 실행 합니다. **코드 분석 실행** FxCop Roslyn 기반 분석기를 포함 하는 Roslyn 기반 분석기를 적용 되지 않습니다.

## <a name="does-the-runcodeanalysis-msbuild-project-property-run-analyzers"></a>RunCodeAnalysis msbuild 프로젝트 속성 분석기를 실행 하나요?

아니요. 합니다 **RunCodeAnalysis** 프로젝트 파일에서 속성 (예를 들어 *.csproj*) 레거시 FxCop 실행에 사용 됩니다. 호출 하는 빌드 후 msbuild 작업을 실행 **FxCopCmd.exe**합니다. 선택 같습니다 **분석** > **코드 분석 실행** Visual Studio에서.

## <a name="so-how-do-i-run-fxcop-analyzers-then"></a>어떻게 실행 합니까 FxCop 분석기 다음?

FxCop 분석기를 처음 실행할 [NuGet 패키지를 설치](install-fxcop-analyzers.md) 에 있습니다. 그런 다음 Visual Studio 또는 msbuild를 사용 하 여 프로젝트 또는 솔루션을 빌드하십시오. 경고 및 FxCop 분석기를 생성 하는 오류에 표시 됩니다는 **오류 목록** 나 명령 창.

## <a name="see-also"></a>참고자료

- [.NET 컴파일러 플랫폼 분석기 개요](roslyn-analyzers-overview.md)
- [분석기를 사용 하 여 시작](fxcop-analyzers.yml)
- [FxCop 분석기를 설치 합니다.](install-fxcop-analyzers.md)
