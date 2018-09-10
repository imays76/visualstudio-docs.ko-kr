---
title: 혼합된 모드 디버깅 Microsoft.NET Framework 4를 사용 하는 경우에 프로세스는 x64 이상을 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a6d58713da9a4c809d5f9c3db6f7157a699a467f
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44284096"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>x64 프로세스의 혼합 모드 디버깅은 Microsoft.NET Framework 4 이상을 사용할 때만 지원됩니다.
4 이전의 .NET Framework 버전에서는 x64 프로세스의 혼합 모드 디버깅을 지원하지 않습니다. 따라서 디버깅하는 동안 네이티브 코드에서 관리 코드로 또는 그 반대로 실행할 수 없습니다.  
  
### <a name="workarounds"></a>해결 방법  
  
-   Microsoft .NET Framework 4 이상을 사용하도록 프로젝트를 업데이트합니다.  
  
     또는  
  
     관리 코드와 네이티브 코드를 별도의 디버깅 세션에서 디버깅합니다.  
  
     또는  
  
     다음 절차에 설명된 대로 혼합 코드를 32비트 프로세스로 디버깅합니다.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>플랫폼을 32비트로 변경하려면(Visual Basic 또는 C#)  
  
1.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.  
  
2.  속성 페이지를 클릭 합니다 **컴파일합니다** 또는 **디버그** 탭 합니다.  
  
3.  클릭 **플랫폼** 플랫폼 목록에서 x86을 선택 합니다.  
  
     기본적으로 Visual Basic 및 C# 컴파일러에서는 모든 CPU에서 실행할 수 있는 코드를 생성합니다. 이러한 이진 코드는 64비트 컴퓨터에서 64비트 프로세스로 실행됩니다. 32 비트 프로세스에서 실행 하려면 선택 해야 합니다 **Win32**가 아닌 **AnyCPU**합니다.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>플랫폼을 32비트로 변경하려면(C/C++)  
  
1.  **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 **속성**합니다.  
  
2.  속성 페이지에서 클릭 **플랫폼** 고 플랫폼 목록에서 Win32를 선택 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   참조 [SQL 디버깅 설정](/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100))합니다.  
  
## <a name="see-also"></a>참고 항목  
 [64비트 응용 프로그램 디버그](../debugger/debug-64-bit-applications.md)