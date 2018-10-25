---
title: '방법: 사용 하도록 설정 하 고 편집 하며 계속 하기를 사용 하지 않도록 설정 (C#, VB, c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 10/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: f0bf354f64be9c03a64beadcffdd7ff1138218df
ms.sourcegitcommit: c5e72875206b8c5737c29d5b1ec7b86eec747303
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2018
ms.locfileid: "49382751"
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>방법: 사용 하도록 설정 하 고 편집 하며 계속 하기를 사용 하지 않도록 설정 (C#, VB, c + +)

사용 하지 않도록 설정 하거나 활성화할 수 있습니다 **편집 하며 계속 하기** Visual studio에서 **옵션** 디자인 타임에 대화 상자. **편집 하며 계속 하기** 빌드 디버그에만 작동 합니다. 자세한 내용은 [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다. 
  
네이티브 c + + **편집 하며 계속 하기** 를 사용 해야는 `/INCREMENTAL` 옵션입니다. C + +의 기능 요구 사항에 대 한 자세한 내용은 참조 [블로그 게시물](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/) 하 고 [편집 하며 계속 하기 (Visual c + +)](../debugger/edit-and-continue-visual-cpp.md)합니다.
  
**편집 하며 계속 하기를 사용할지 설정 합니다.**  
  
1.  디버깅 세션의 경우 디버깅을 중지 (**디버깅할** > **디버깅 중지** 하거나 **Shift**+**F5**) .

1.  **도구가** > **옵션** > (또는 **디버그** > **옵션**) > **디버깅**  >  **일반**선택 **편집 하며 계속 하기** 오른쪽 창에서.  
  
    > [!NOTE]
    >  IntelliTrace를 사용하도록 설정되어 있고 IntelliTrace 이벤트 및 호출 정보를 모두 수집하는 경우 편집하며 계속하기를 사용하지 않도록 설정됩니다. 자세한 내용은 [IntelliTrace](../debugger/intellitrace.md)합니다.
    
1.  C + + 코드에 대 한 했는지 **네이티브 편집 하며 계속 하기** 선택 하 고 추가 옵션을 설정 합니다.
    - **변경 내용 적용 (네이티브 전용)를 계속할 때**  
      
      선택 하면 Visual Studio 자동으로 컴파일하고 중단 상태에서 디버깅을 계속 하면 코드 변경 내용을 적용 합니다. 그렇지 않은 경우 사용 하 여 변경 내용을 적용 하도록 선택할 수 있습니다 **디버깅할** > **코드 변경 내용 적용**합니다.  
      
    - **(네이티브 전용) 부실 코드 경으십시오**  
      
      선택 하 고, 부실 코드 경고를 제공 합니다. 
  
1.  **확인**을 클릭합니다.    
