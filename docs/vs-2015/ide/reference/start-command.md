---
title: 시작 명령 | Microsoft Docs
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
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a3b2f482fb33664796a4e6fe451a6a2917e9592f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49247718"
---
# <a name="start-command"></a>시작 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
시작 프로젝트 디버깅을 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>인수  
 `address`  
 선택 사항입니다. 소스 코드의 중단점처럼 프로그램에서 실행을 일시 중단하는 주소입니다. 이 인수는 디버그 모드에서만 유효합니다.  
  
## <a name="remarks"></a>설명  
 **시작** 명령을 실행하면 지정된 주소로 RunToCursor 작업을 수행합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 디버거를 시작하고 발생하는 모든 예외를 무시합니다.  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



