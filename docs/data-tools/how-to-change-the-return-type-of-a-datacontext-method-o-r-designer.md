---
title: '방법: DataContext 메서드 (O-r 디자이너)의 반환 형식 변경'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5c67d6dea4c64e858acdab25ecc4a6cede6bf262
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089359"
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>방법: DataContext 메서드 (O/R 디자이너)의 반환 형식 변경
반환 형식을 <xref:System.Data.Linq.DataContext> 저장된 프로시저를 삭제 하거나 함수에 따라 달라 집니다 (저장된 프로시저 또는 함수에 따라 만든) 메서드를 **O/R 디자이너**합니다. 저장 프로시저 또는 함수에서 반환된 데이터의 스키마가 엔터티 클래스의 모양과 일치하는 경우 항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 빈 영역으로 항목을 삭제 하는 경우는 **O/R 디자이너**, <xref:System.Data.Linq.DataContext> 자동으로 생성 된 형식을 반환 하는 메서드가 만들어집니다. 메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다. 반환 형식을 검사 하거나 변경 하는 <xref:System.Data.Linq.DataContext> 메서드를 선택 하 고 클릭 합니다 **반환 형식** 속성에는 **속성** 창.

> [!NOTE]
>  되돌릴 수 없습니다 <xref:System.Data.Linq.DataContext> 반환 형식을 엔터티 클래스를 사용 하 여 자동으로 생성 된 형식을 반환 하도록 설정 하는 메서드를 **속성** 창입니다. 되돌리려면를 <xref:System.Data.Linq.DataContext> 는 자동으로 생성 된 형식을 반환 하는 방법 원래 데이터베이스 개체를 끌어 놓아야 합니다 **O/R 디자이너** 다시 합니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>DataContext 메서드의 반환 형식을 자동으로 생성된 형식에서 엔터티 클래스로 변경하려면

1.  메서드 창에서 <xref:System.Data.Linq.DataContext> 메서드를 선택합니다.

2.  선택 **반환 형식** 에 **속성** 창을 선택한 다음 사용 가능한 엔터티 클래스를 **반환 형식** 목록입니다. 원하는 엔터티 클래스가 목록에 없는 경우 추가 하거나에서 만들어 합니다 **O/R 디자이너** 목록에 추가 합니다.

3.  저장 된 *.dbml* 파일입니다.

## <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>DataContext 메서드의 반환 형식을 엔터티 클래스에서 자동으로 생성된 형식으로 다시 변경하려면

1.  선택 합니다 <xref:System.Data.Linq.DataContext> 에서 메서드를 **메서드** 창을 삭제 합니다.

2.  데이터베이스 개체를 끌어서 **서버 탐색기** 하거나 **데이터베이스 탐색기** 의 빈 영역으로는 **O/R 디자이너**합니다.

3.  저장 된 *.dbml* 파일입니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)
- [방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 메서드 만들기](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)