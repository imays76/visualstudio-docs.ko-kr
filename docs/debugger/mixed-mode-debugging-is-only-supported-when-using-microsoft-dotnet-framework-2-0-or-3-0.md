---
title: Microsoft.NET Framework 2.0 또는 3.0을 사용 하는 경우에 지원 됩니다 혼합된 모드 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 9d51a0ca72840b20e23eaaa9db3a82382a3fa012
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44284070"
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>혼합 모드 디버깅은 Microsoft .NET Framework 2.0 또는 3.0을 사용할 때만 지원됩니다.
2.0 이전 버전의 Microsoft .NET Framework에서는 64비트 프로세스의 혼합 모드 디버깅이 지원되지 않습니다. 즉, 디버깅하는 동안 네이티브 코드에서 관리 코드로 또는 그 반대로 이동할 수 없습니다.  
  
 이 문제를 해결하기 위해 다음을 수행할 수 있습니다.  
  
-   Microsoft .NET Framework 2.0 또는 3.0을 사용하도록 프로젝트를 업데이트합니다.  
  
-   관리 코드와 네이티브 코드를 별도의 디버깅 세션에서 디버깅합니다.  
  
-   다음 절차에 설명된 대로 혼합 코드를 32비트 프로세스로 디버깅합니다.  
  
### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>운영 체제를 32비트로 변경하려면(Visual Basic 또는 C#)  
  
1.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성** 바로 가기 메뉴에 있습니다.  
  
2.  속성 페이지를 클릭 합니다 **컴파일합니다** 또는 **디버그** 탭 합니다.  
  
3.  클릭 **플랫폼**를 선택한 후 **x86** 플랫폼 목록에서.  
  
     기본적으로 Visual Basic 및 C# 컴파일러에서는 모든 CPU에서 실행할 수 있는 코드가 생성됩니다. 이러한 이진 코드는 64비트 컴퓨터에서 64비트 프로세스로 실행됩니다. 32 비트 프로세스에서 실행 하려면 선택 해야 합니다 **Win32**가 아닌 **AnyCPU**합니다.  
  
### <a name="to-change-the-operating-system-to-32-bit-cc"></a>운영 체제를 32비트로 변경하려면(C/C++)  
  
1.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성** 바로 가기 메뉴에 있습니다.  
  
     속성 페이지에서 클릭 **플랫폼**를 선택한 후 **Win32** 플랫폼 목록에서.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   참조 [SQL 디버깅 설정](/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100))합니다.  
  
## <a name="see-also"></a>참고 항목  
 [64비트 응용 프로그램 디버그](../debugger/debug-64-bit-applications.md)