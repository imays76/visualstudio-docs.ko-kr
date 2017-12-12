---
title: "코드 생성 (C#)는 추상 클래스 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 301c4f7a8955f22952787c78eaeabff826495c29
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="implement-an-abstract-class-in-c"></a>C#에서 추상 클래스를 구현 합니다. #
**:** 즉시 추상 클래스를 구현 하는 데 필요한 코드를 생성할 수 있습니다. 

**경우:** 추상 클래스에서 상속 하려는 경우.  

**이유:** 이 기능에서 모든 메서드 시그니처를 자동으로 생성 되지만 모든 추상 멤버 하나씩 여을 수동으로 구현할 수 있습니다. 

**방법:**

1. 줄에 커서를 놓고 추상 클래스에서 상속 했 있지만 모든 필수 멤버를 구현 하지 나타내는 빨간색 물결 기호는 합니다.

   ![강조 표시 된 코드](media/abstract_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **추상 클래스 구현** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 선택 **추상 클래스 구현** 미리 보기 창 팝업에서 합니다.
     * 빨간색 물결 기호 위로 마우스를 클릭 하 고 ![전구](media/bulb.png) 표시 되는 아이콘입니다.
     * 클릭 하 고 ![전구](media/bulb.png) 커서가 있는 경우 텍스트 이미 빨간색 물결 기호는 줄에 왼쪽된 여백에 표시 되는 아이콘입니다.

   ![구현 클래스 미리 보기](media/abstract_preview.png)

   >[!TIP]
   >사용 하 여는 [ **변경 내용 미리 보기가** ](../../ide/preview-changes.md) 모두 선택 하기 전에 적용 될 변경 내용을 보려면 미리 보기 창의 맨 아래에 링크 합니다.
   >
   >또한 사용할 수는 **문서**, **프로젝트**, 및 **솔루션** 여러 간의 적절 한 메서드 서명을 위해 미리 보기 창의 맨 아래에 링크 추상 클래스에서 상속 된 클래스입니다.

1. 추상 메서드 시그니처를 구현할 준비가 자동으로 만들 수 있습니다.

   ![클래스의 결과 구현 합니다.](media/abstract_result.png)

## <a name="see-also"></a>참고 항목  
[코드 생성(C#)](../code-generation-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)