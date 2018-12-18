---
title: 선택한 클래스는 하나 이상의 DataContext 메서드의 반환 형식으로 사용 되므로 삭제할 수 없습니다 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 084843636d62bd7d85c5bbc141aa0fe8ddf81462
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49236264"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>선택한 클래스가 하나 이상의 DataContext 메서드의 반환 형식으로 사용되므로 해당 클래스를 삭제할 수 없습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
하나 이상의 <xref:System.Data.Linq.DataContext> 메서드 반환 형식은 선택한 엔터티 클래스입니다. <xref:System.Data.Linq.DataContext> 메서드의 반환 형식으로 사용되는 엔터티 클래스를 삭제하면 프로젝트를 컴파일할 수 없습니다. 선택한 엔터티 클래스를 삭제하려면 해당 엔터티 클래스를 사용하는 <xref:System.Data.Linq.DataContext> 메서드를 식별하고 해당 메서드의 반환 형식을 서로 다른 엔터티 클래스로 설정합니다.  
  
 반환 형식으로 되돌리려면 <xref:System.Data.Linq.DataContext> 메서드는 원래 자동으로 생성 된 형식으로 먼저 삭제 합니다 <xref:System.Data.Linq.DataContext> 메서드 창에서 메서드 한 다음 개체를 끌어 **서버 탐색기** / **데이터베이스 탐색기** O/R 디자이너로 다시 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  식별 <xref:System.Data.Linq.DataContext> 반환 형식으로 선택 하 여 엔터티 클래스를 사용 하는 메서드를 <xref:System.Data.Linq.DataContext> 메서드에서 메서드 창 및 검사는 **반환 형식** 속성에는 **속성** 창 .  
  
2.  설정 된 **반환 형식** 서로 다른 엔터티 클래스로 또는 삭제는 <xref:System.Data.Linq.DataContext> 메서드 창에서 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)   
 [방법: DataContext 메서드의 반환 형식 변경(O/R 디자이너)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)

