---
title: 소스 열거 명령 | Microsoft 문서
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
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ff216ddd8943ea971669c6ebb1c7c0306b02160f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49171979"
---
# <a name="list-source-command"></a>소스 목록 표시 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
소스 코드의 지정된 줄을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>스위치  
 /Count:`number`  
 선택 사항입니다. 표시할 줄 수를 지정합니다.  
  
 /Current  
 선택 사항입니다. 현재 줄을 표시합니다.  
  
 /File:`filename`  
 선택 사항입니다. 표시할 파일의 경로입니다. 파일 이름이 지정되지 않은 경우 이 명령은 현재 문의 줄에 대한 소스 코드를 표시합니다.  
  
 /Line:`number`  
 선택 사항입니다. 특정 줄 번호를 표시합니다.  
  
 /ShowLineNumbers:`yes|no`  
 선택 사항입니다. 줄 번호를 표시할지 여부를 지정합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 이 예제에서는 줄 번호를 표시하여 Form1.vb 파일의 줄 4 소스 코드를 나열합니다.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)



