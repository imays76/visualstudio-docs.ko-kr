---
title: 'F # 디버깅 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5790b81eedb1a1bb9dc65b7ce053089c3bc1470
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541462"
---
# <a name="debugging-f"></a>F# 디버깅 #
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [디버깅 F #](https://docs.microsoft.com/visualstudio/debugger/debugging-f-hash)합니다.  
  
F# 디버깅은 다음과 같은 몇 가지 예외를 제외하고는 관리되는 언어 디버깅과 비슷합니다.  
  
-   합니다 **자동** 창 F # 변수가 표시 되지 않습니다.  
  
-   F#의 경우에는 편집하며 계속하기가 지원되지 않습니다. 디버깅 세션 중에 F# 코드를 편집할 수는 있지만 편집해서는 안 됩니다. 디버깅 세션 중에는 코드 변경 내용이 적용되지 않으므로 디버깅 중에 F# 코드를 편집하면 소스 코드와 디버깅되는 코드가 일치하지 않습니다.  
  
-   디버거에서는 F# 식을 인식하지 못합니다. F# 디버깅 중에 디버거 창이나 디버거 대화 상자에 식을 입력하려면 식을 C# 구문으로 변환해야 합니다. F# 식을 C# 식으로 변환할 때는 같은지 비교하는 연산자로 C#에서는 ==을 사용하고 F#에서는 단일 =을 사용한다는 점에 유의해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드 디버그](../debugger/debugging-managed-code.md)


