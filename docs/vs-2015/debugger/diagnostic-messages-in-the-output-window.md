---
title: 출력 창의 진단 메시지 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.output
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa2e01859190b4e22f076892b23595c4617a29f0
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49951303"
---
# <a name="diagnostic-messages-in-the-output-window"></a>출력 창에 표시되는 진단 메시지
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:System.Diagnostics> 클래스 라이브러리에 포함된 Debug 클래스 또는 Trace 클래스를 사용하여 출력 창에 런타임 메시지를 표시할 수 있습니다. 디버그 버전 프로그램에서만 출력할 경우에는 Debug 클래스를 사용하십시오. 디버그 및 릴리스 버전에서 모두 출력하려면 Trace 클래스를 사용하십시오.  
  
## <a name="output-methods"></a>출력 메서드  
 <xref:System.Diagnostics.Trace> 클래스와 <xref:System.Diagnostics.Debug> 클래스에는 다음과 같은 출력 메서드가 있습니다.  
  
- 실행을 중단하지 않고 정보를 출력하는 여러 가지 `Write` 메서드. 이 메서드는 이전 Visual Basic 버전의 `Debug.Print` 메서드 대신 사용됩니다.  
  
- 지정된 조건이 실패할 경우 실행을 중단하고 정보를 출력하는 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 메서드. 기본적으로 `Assert` 메서드는 해당 정보를 대화 상자에 표시합니다. 자세한 내용은 [관리 코드에 어설션](../debugger/assertions-in-managed-code.md)합니다.  
  
- 항상 실행을 중단하고 정보를 출력하는 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> 메서드. 기본적으로 `Fail` 메서드는 정보를 대화 상자에 표시합니다.  
  
  응용 프로그램에서 프로그램 출력 이외에 **출력** 창에 대 한 정보를 표시할 수 있습니다.  
  
- 디버거에서 로드하거나 언로드한 모듈 정보  
  
- throw된 예외 정보  
  
- 종료되는 프로세스 정보  
  
- 종료되는 스레드 정보  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [출력 창](../ide/reference/output-window.md)   
 [응용 프로그램 추적 및 조율](http://msdn.microsoft.com/library/773b6fc4-9013-4322-b728-5dec7a72e743)   
 [계측 및 추적 소개](http://msdn.microsoft.com/en-us/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)   
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [관리 코드 디버그](../debugger/debugging-managed-code.md)



