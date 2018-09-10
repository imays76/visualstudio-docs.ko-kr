---
title: 혼합 모드 응용 프로그램 디버그 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging, property evaluation
- Call Stack window
- mixed-mode debugging
- Call Stack window, mixed-mode debugging
- debugging managed code, mixed code
- mixed-mode debugging, call stack
ms.assetid: 60e34477-ae4e-48c7-9093-3e37f72e1bc3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 795b1bf9f2c3d2014e1fa2c4ccd25254a07a70a8
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283316"
---
# <a name="debugging-mixed-mode-applications"></a>혼합 모드 응용 프로그램 디버깅
혼합 모드 응용 프로그램은 네이티브 코드(C++)와 관리 코드(Visual Basic, Visual C# 또는 C++처럼 공용 언어 런타임에서 실행되는 코드)가 결합된 응용 프로그램입니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 혼합 모드 응용 프로그램의 디버깅이 대부분 투명하게 이루어지며 단일 모드 응용 프로그램을 디버깅할 때와 크게 다르지 않습니다. 그러나 특별히 몇 가지 사항을 고려해야 합니다.  
  
## <a name="enable-c-edit-and-continue-in-mixed-mode-debugging"></a>혼합 모드 디버깅에서 C++ 편집하며 계속하기 사용  

C + + 용 편집 하며 계속 하기를 사용 하려면 [을 사용 하도록 설정 하 고 편집 하며 계속 하기를 사용 하지 않도록 설정 하는 방법을](../debugger/how-to-enable-and-disable-edit-and-continue.md)합니다.

> [!NOTE]
> Visual Studio 2013에서 C++에 대한 편집하며 계속하기를 사용하려면 레거시 디버깅 엔진으로 되돌려야 합니다. 참조 [Visual Studio 2013에서 관리 되는 호환성 모드를 전환](https://blogs.msdn.microsoft.com/devops/2013/10/16/switching-to-managed-compatibility-mode-in-visual-studio-2013/) Microsoft 애플리케이션 수명 주기 관리 블로그.  
  
## <a name="property-evaluation-in-mixed-mode-applications"></a>혼합 모드 응용 프로그램의 속성 확인  
 혼합 모드 응용 프로그램에서 디버거의 속성 확인 작업은 많은 리소스를 차지합니다. 그러므로 단계별 실행과 같은 디버깅 작업이 느리게 나타날 수 있습니다. 자세한 내용은 [단계별 실행](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ek13f001(v=vs.100))합니다. 혼합 모드 디버깅의 성능이 좋지 않을 경우에는 디버거 창에서 속성 확인을 해제할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
#### <a name="to-turn-off-property-evaluation"></a>속성 확인을 해제하려면  
  
1.  **도구** 메뉴에서 **옵션**을 선택합니다.  
  
2.  에 **옵션** 대화 상자를 엽니다는 **디버깅** 폴더를 선택 합니다 **일반** 범주입니다.  
  
3.  선택을 취소 합니다 **속성 확인 및 기타 암시적 함수 호출** 확인란 합니다.  
  
 네이티브 호출 스택과 관리되는 호출 스택이 서로 다르기 때문에 디버거는 혼합 코드에 대한 완전한 호출 스택을 항상 제공할 수는 없습니다. 네이티브 코드가 관리 코드를 호출할 경우 약간 다를 수 있습니다. 자세한 내용은 [혼합 코드 및 호출 스택 창에서 누락 된 정보](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드 디버그](../debugger/debugging-managed-code.md)