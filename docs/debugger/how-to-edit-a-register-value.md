---
title: '방법: 레지스터 값 편집 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.register.edit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d0337f7c77d1ed601c7a6c13c702f4758cbfdbd
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257084"
---
# <a name="how-to-edit-a-register-value-c-c-visual-basic-f"></a>방법: 레지스터 값 편집 (C#, c + +, Visual Basic의 경우 F#)

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