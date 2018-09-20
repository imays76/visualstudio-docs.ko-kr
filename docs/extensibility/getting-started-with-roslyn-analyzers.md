---
title: Roslyn 분석기 시작 | Microsoft Docs
ms.date: 04/02/2018
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 41db830fbf7dcbe97f44d64ffa9b9701ec658c1e
ms.sourcegitcommit: 3dd15e019cba7d35dbabc1aa3bf55842a59f5278
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46370590"
---
# <a name="get-started-with-roslyn-analyzers"></a>Roslyn 분석기 시작

Visual Studio에서 프로젝트 기반 라이브 코드 분석기를 사용 하 여 API 작성자는 NuGet 패키지의 일부로 도메인 관련 코드 분석을 제공할 수 있습니다. 이러한 분석기는.NET 컴파일러 플랫폼 (코드 이름된 "Roslyn")에서 구동 되, 때문에 (빌드 문제를 검색 하는 코드를 더 이상 대기) 줄을 마친 전이라를 입력할 때 코드에서 경고를 생성할 수 있으므로 합니다. 분석기는 자동 코드 수정 사항을 즉시 코드 정리 수 Visual Studio 전구 프롬프트를 통해 발생할 수도 수 있습니다.

## <a name="get-started"></a>시작

[Roslyn 라이브 코드 분석기 소개와 연습은](https://msdn.microsoft.com/magazine/dn879356.aspx)

[추가 코드 수정 연습: 사용자 수정 분석기 문제에 대 한 제공](https://msdn.microsoft.com/magazine/dn904670.aspx)

[소개와 연습은 실제 분석기의 이야기](https://channel9.msdn.com/events/Build/2015/3-725)

[실제 Roslyn 분석기](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) 로 볼 수 있는 한 [통신](https://channel9.msdn.com/events/Build/2015/3-725)

[세 가지 유형의 분석기를 그룹화 하는 github에서 몇 가지 예제](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[소개과 몇 가지 분석기 둘러보기](https://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>참고자료

- [Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
- [OSS github 사이트에서 더 많은 문서](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [GitHub의 Roslyn 분석기를 사용 하 여 구현 하는 FxCop 규칙](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)