---
title: Win32 오류 코드를 어디에서 찾을 수 있습니까? | Microsoft 문서
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
- vc.errors
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0606463eafc5c681aacaef9fb4111f71260ecb7
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51723742"
---
# <a name="where-can-i-look-up-win32-error-codes"></a>Win32 오류 코드를 어디에서 찾을 수 있습니까?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

기본 시스템 설치의 INCLUDE 디렉터리에 있는 WINERROR.H에는 Win32 API 함수에 대한 오류 코드 정의가 포함되어 있습니다.  
  
 코드를 입력 하 여 오류 코드를 조회할 수 있습니다 합니다 **Watch** 창 또는 **간략 한 조사식** 대화 상자. 예를 들어:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그 Faq](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)



