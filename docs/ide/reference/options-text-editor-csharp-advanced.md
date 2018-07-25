---
title: 옵션, 텍스트 편집기, C#, 고급
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: ab08de0c6993f57c719f69ccf27e30e3cbe41c32
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433304"
---
# <a name="options-text-editor-c-advanced"></a>옵션, 텍스트 편집기, C#, 고급

**고급** 옵션을 사용하여 
C#의 편집기 서식, 코드 리팩터링 및 XML 문서 주석에 대한 설정을 수정합니다. 이 옵션 페이지에 액세스하려면 **도구** > **옵션**을 선택한 다음, **텍스트 편집기** > **C#** > **고급**을 선택합니다.

> [!NOTE]
> 모든 옵션이 여기에 나열되지는 않습니다.

## <a name="analysis"></a>분석

- 전체 솔루션 분석 사용

   열린 코드 파일뿐만 아니라 솔루션의 모든 파일에 대해 코드 분석을 사용할 수 있습니다. 자세한 내용은 [전체 옵션 분석](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)을 참조하세요.

## <a name="highlighting"></a>강조 표시

- 커서 아래의 기호에 대한 참조 강조

   기호 내부에 커서를 놓거나 기호를 클릭하면 코드 파일에 있는 해당 기호의 모든 인스턴스가 강조 표시됩니다.

## <a name="outlining"></a>개요

- 개요 모드로 파일 열기

   이 옵션을 선택하면 축소 가능한 코드 블록을 만드는 코드 파일이 자동으로 요약됩니다. 파일이 처음 열리면 #regions 블록 및 비활성 코드 블록이 축소됩니다.

## <a name="editor-help"></a>편집기 도움말

- ///에 대해 XML 문서 주석 생성

   이 옵션을 선택한 경우 `///` 주석 도입부를 입력한 후 XML 문서 주석에 대한 XML 요소를 삽입합니다. XML 문서에 대한 자세한 내용은 [XML 문서 주석(C# 프로그래밍 가이드)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [방법: 문서 생성에 대한 XML 주석 삽입](../../ide/reference/generate-xml-documentation-comments.md)
- [XML 문서 주석(C# 프로그래밍 가이드)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [XML 주석을 사용하여 코드 문서화(C# 가이드)](/dotnet/csharp/codedoc)
- [언어별 편집기 옵션 설정](../../ide/reference/setting-language-specific-editor-options.md)
- [C# IntelliSense](../../ide/visual-csharp-intellisense.md)