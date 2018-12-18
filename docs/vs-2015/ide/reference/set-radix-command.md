---
title: 기수 설정 명령 | Microsoft 문서
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f0df00cf4c1d1264692be5ab5313eb9f03920b3c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49296129"
---
# <a name="set-radix-command"></a>기수 설정 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
정수 값을 표시하는 데 사용할 숫자 기준을 설정하거나 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.SetRadix [10 | 16 | hex | dec]  
```  
  
## <a name="arguments"></a>인수  
 `10`, `16`, `hex` 또는 `dec`  
 선택 사항입니다. 10진수(10 또는 dec) 또는 16진수(16 또는 hex)를 나타냅니다. 인수를 생략하면 현재 기수 값이 반환됩니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 16진수 형식의 정수 값을 표시하도록 환경을 설정합니다.  
  
```  
>Debug.SetRadix hex  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



