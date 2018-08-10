---
title: 선택한 클래스가 하나 이상의 DataContext 메서드의 반환 형식으로 사용되므로 해당 클래스를 삭제할 수 없습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 21ef0f86d701c899328044a03cde8035a1e7292d
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174213"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>선택한 클래스가 하나 이상의 DataContext 메서드의 반환 형식으로 사용되므로 해당 클래스를 삭제할 수 없습니다.

하나 이상의 <xref:System.Data.Linq.DataContext> 메서드 반환 형식은 선택한 엔터티 클래스입니다. 에 대 한 반환 형식으로 사용 되는 엔터티 클래스를 삭제 한 <xref:System.Data.Linq.DataContext> 메서드를 사용 하면 프로젝트를 컴파일하는 합니다. 선택한 엔터티 클래스를 삭제하려면 해당 엔터티 클래스를 사용하는 <xref:System.Data.Linq.DataContext> 메서드를 식별하고 해당 메서드의 반환 형식을 서로 다른 엔터티 클래스로 설정합니다.

반환 형식으로 되돌리려면 <xref:System.Data.Linq.DataContext> 메서드는 원래 자동으로 생성 된 형식으로 먼저 삭제 합니다 <xref:System.Data.Linq.DataContext> 메서드에서 **메서드** 창 한 다음 개체를 끌어 **서버 탐색기** / **데이터베이스 탐색기** 에 **O/R 디자이너** 다시 합니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 식별 <xref:System.Data.Linq.DataContext> 반환 형식으로 선택 하 여 엔터티 클래스를 사용 하는 메서드를 <xref:System.Data.Linq.DataContext> 에서 메서드는 **메서드** 창과 검사를 **반환 형식** 속성에는 **속성** 창입니다.

2. 설정 된 **반환 형식** 서로 다른 엔터티 클래스로 또는 삭제는 <xref:System.Data.Linq.DataContext> 메서드 창에서 메서드.

## <a name="see-also"></a>참고자료

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)