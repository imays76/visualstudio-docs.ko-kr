---
title: 자식 속성을 가진 속성 숨기기 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties [Visual Studio SDK], hiding
- Properties window, hiding properties that have child properties
ms.assetid: 6003607e-fc19-4bf9-a299-9f6adf8e92eb
caps.latest.revision: 13
manager: douge
ms.openlocfilehash: bd340b748311bbb257ed0c4bbfe7b972cbf7beb9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554856"
---
# <a name="hiding-properties-that-have-child-properties"></a>자식 속성을 가진 속성 숨기기
자식 속성을 가진 속성 숨기기 하려고 합니다.  
  
-   프로젝트 중첩 된 경우 부모 프로그래밍 방식으로 프로젝트 자식 프로젝트의 일부 측면을 제어 합니다.  
  
-   컨트롤을 사용 하 여 특수 한 디자이너를 사용 하 여 컨트롤의 모든 속성에 대 한 모든 권한을 개발자에 게를 제공 하지 않을 경우.  
  
-   개체의 소유권 범위 속성 보기를 제한 하려는 경우.  
  
### <a name="to-hide-properties-that-have-child-properties"></a>자식 속성을 가진 속성을 숨기려면  
  
1.  설정 된 `pfDisplay` 에서 매개 변수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties%2A> 에 `FALSE`입니다.  
  
2.  설정 된 `pfHide` 에서 매개 변수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> 에 `TRUE`입니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 눈금 표시](../extensibility/internals/properties-display-grid.md)