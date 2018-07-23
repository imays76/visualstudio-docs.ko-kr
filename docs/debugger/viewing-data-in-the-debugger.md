---
title: 디버거에서 데이터의 사용자 지정 뷰 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 06/27/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02bb65aa2b0601315a3f5dec2cc9459af210db3e
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39177674"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger"></a>Visual Studio 디버거에서 데이터의 사용자 지정 뷰 만들기
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거는 프로그램의 상태를 검사하고 수정하는 여러 가지 도구를 제공합니다. 이러한 도구의 대부분은 중단 모드에서만 작동합니다.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>변수 창과 데이터 팁에서 데이터의 사용자 지정 뷰 만들기
 많은 합니다 [디버거 창](../debugger/debugger-windows.md)와 같은 **자동** 및 **조사식** windows를 사용 하면 디버깅 하는 동안 변수를 검사 하 합니다. 기본 형식 및 디버거 변수 창에서 관리 되는 개체의 표시를 사용자 지정할 수 있습니다 [DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md)합니다. 이 응용 프로그램에서 만든 형식을 표시 하려면 유용할 수 있습니다. 자세한 내용은 [네이티브 개체의 사용자 지정 뷰 만들기](../debugger/create-custom-views-of-native-objects.md) 하 고 [관리 되는 개체의 사용자 지정 뷰 만들기](../debugger/create-custom-views-of-dot-managed-objects.md)합니다.
  
## <a name="create-custom-visualizers"></a>사용자 지정 시각화 도우미 만들기  
 시각화 도우미를 사용 하는 의미 있는 방식으로 개체 또는 변수 내용을 볼 수 있습니다. Visual Studio 디버거 시각화 도우미 돋보기 아이콘을 사용 하 여 열 수 있는 다른 windows 가리킵니다 ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "시각화 아이콘")합니다. 예를 들어, HTML 시각화 도우미를 사용하면 HTML 문자열을 브라우저에서 해석되고 표시되는 방식대로 볼 수 있습니다. DataTips, **조사식** 창, **자동** 창, **지역** 창 또는 **간략한 조사식** 대화 상자에서 시각화 도우미에 액세스할 수 있습니다. 자세한 내용은 [사용자 지정 시각화 도우미 만들기](../debugger/create-custom-visualizers-of-data.md)합니다.
  
## <a name="see-also"></a>참고 항목  
 [Debugger Basics](../debugger/getting-started-with-the-debugger.md) (디버거 기본 사항)  
 [명령 창](../ide/reference/command-window.md)   
 [디버거 보안](../debugger/debugger-security.md)