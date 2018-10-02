---
title: 이동 명령 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 123398be5bf8b4aece11e2624390507cec2252d0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550544"
---
# <a name="go-to-command"></a>이동 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [명령에 이동](https://docs.microsoft.com/visualstudio/ide/reference/go-to-command)합니다.  
  
  
지정된 줄로 커서를 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Edit.GoTo [linenumber]  
```  
  
## <a name="arguments"></a>인수  
 `linenumber`  
 선택 사항입니다. 이동할 줄 번호를 나타내는 정수입니다.  
  
## <a name="remarks"></a>설명  
 줄 번호는 1부터 시작합니다. `linenumber` 값이 1보다 작은 경우 첫 번째 줄이 표시됩니다. `linenumber` 값이 마지막 줄 번호보다 큰 경우 마지막 줄이 표시됩니다.  
  
 `linenumber` 값이 지정되지 않으면 **줄 이동** 대화 상자가 표시됩니다.  
  
 이 명령에 대한 별칭은 GoToLn입니다.  
  
## <a name="example"></a>예제  
  
```  
>Edit.GoTo 125  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)



