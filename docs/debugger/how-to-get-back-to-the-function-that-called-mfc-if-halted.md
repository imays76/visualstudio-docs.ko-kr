---
title: '방법: 중지 된 경우 MFC를 호출한 함수로 돌아갈 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da15793027eb643078771d33464258fea73fec9d
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283394"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>방법: 중지된 경우 MFC를 호출한 함수로 돌아가기
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 사용 하는 경우는 **중단** 명령을 합니다 **디버그** 프로그램을 중지 하려면 메뉴, MFC에서 중지 되었고 코드에서 문제 인지 호출 스택 창을 사용 하 여 함수를 다시 탐색 하 합니다. 자세한 내용은 [방법: 호출 스택 창을 사용 하 여](../debugger/how-to-use-the-call-stack-window.md)입니다.  
  
 때로는 코드가 메시지 펌프에서 손상될 수도 있습니다. 그럴 경우 호출 스택에는 사용자 코드가 들어 있지 않습니다. 이 문제를 방지 하려면 중단점 (사용 하 여 조건 및 적중된 횟수) 대신 사용할 수 있습니다 합니다 **중단** 명령입니다. 자세한 내용은 [중단점 및 추적점](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583)합니다.  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>MFC를 호출한 함수를 탐색하려면  
  
-   사용 된 **호출 스택** 창입니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그 Faq](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)