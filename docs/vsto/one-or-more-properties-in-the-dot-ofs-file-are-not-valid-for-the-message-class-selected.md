---
title: .ofs 파일에 있는 하나 이상의 속성을 선택한 메시지 클래스에 사용할 수 없습니다.
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6d6469c48def1a5d21eb160cb4ad6d14704bc101
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53909127"
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>.ofs 파일에 있는 하나 이상의 속성을 선택한 메시지 클래스에 사용할 수 없습니다.
  이 오류 Outlook에서 디자인 한 양식 영역을 가져올 때 나타나지만 양식 영역의 하나 이상의 필드의 마지막 페이지에서 선택 하는 메시지 클래스와 호환 되지 않습니다 합니다 **새 양식 영역** 마법사.  

예를 들어 **새 양식 영역** 마법사의 마지막 페이지에서 **작업(IPM.Task)** 을 선택할 수 있습니다. 양식 영역에 있는 경우는 **근무지** 필드를 작업에 회사 주소가 없기 때문에이 오류가 표시 됩니다. 따라서 합니다 **근무지** 필드와 호환 되지 않습니다.는 `IPM.Task` message 클래스.  
  
 선택할 수 있습니다 **작업 IPM (합니다. 작업)** 의 마지막 페이지에는 **새 양식 영역** 마법사. 양식 영역에 있는 경우는 **근무지** 필드를 작업에 회사 주소가 없기 때문에이 오류가 표시 됩니다. 따라서 합니다 **근무지** 필드와 호환 되지 않습니다.는 `IPM.Task` message 클래스.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   **새 양식 영역** 마법사의 마지막 페이지에서 양식 영역의 필드와 호환되는 메시지 클래스를 선택합니다.  
  
-   Outlook의 Forms 디자이너에서 메시지 클래스와 호환 되지 않는 필드를 제거 합니다. 마지막 페이지에서 선택 하려는 필드를 제거 합니다 **새 양식 영역** 마법사.  
  
## <a name="see-also"></a>참고 항목  
 [연습: Outlook에서 디자인 한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
