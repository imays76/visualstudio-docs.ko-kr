---
title: '방법: 레지스터 값 편집 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.register.edit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 465ecd4e8003b82a0a7dfbab33004ef2b80d7f32
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553285"
---
# <a name="how-to-edit-a-register-value"></a>방법: 레지스터 값 편집
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 레지스터 값 편집](https://docs.microsoft.com/visualstudio/debugger/how-to-edit-a-register-value)합니다.  
  
레지스터 창에서 주소 수준 디버깅을 설정한 경우에 가능 합니다 **옵션** 대화 상자에서 **디버깅** 노드.  
  
### <a name="to-change-the-value-of-a-register"></a>레지스터 값을 변경하려면  
  
1.  에 **등록** 창에서 사용 하 여 TAB 키 또는 마우스를 움직여 삽입 변경 하려는 값을 가리킵니다. 입력하기 시작할 때 덮어 쓰려는 값 앞에 커서가 있어야 합니다.  
  
2.  새 값을 입력합니다.  
  
    > [!CAUTION]
    >  레지스터 값을 변경하면(특히 EIP 및 EBP 레지스터에서) 프로그램 실행에 변경된 값이 적용됩니다.  
  
    > [!CAUTION]
    >  부동 소수점 값을 편집하면 소수 부분이 10진수에서 이진수로 변환되면서 약간의 오차가 발생할 수 있습니다. 겉보기에 변화가 없는 편집 작업을 수행하는 경우에도 부동 소수점 변수의 LSB 중 일부가 변경될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 레지스터 창 사용](../debugger/how-to-use-the-registers-window.md)





