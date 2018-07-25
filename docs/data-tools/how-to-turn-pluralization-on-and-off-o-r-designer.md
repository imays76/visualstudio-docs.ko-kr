---
title: '방법: 복수형 설정 및 해제 (O-r 디자이너)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0a2d2e44efc284c38cfc450833839776effb9936
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089385"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>방법: 복수형 설정 및 해제 (O/R 디자이너)
기본적으로 이름이 s 또는 ies로 끝나는 데이터베이스 개체를 끌면 **서버 탐색기** 또는 **데이터베이스 탐색기** 에 [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md), 생성된 된 엔터티 클래스의 이름은 복수형에서 단수형으로 변경 됩니다. 이렇게 하면 인스턴스화된 엔터티 클래스를 데이터의 단일 레코드에 매핑하는 것을 보다 정확하게 나타낼 수 있습니다. 예를 들어, 추가 `Customers` 테이블의 **O/R 디자이너** 라는 엔터티 클래스가 결과 `Customer` 클래스는 단일 고객을 위한 데이터를 저장 하기 때문에.

> [!NOTE]
>  복수 적용은 기본적으로 Visual Studio 영어 버전에만 적용됩니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-turn-pluralization-on-and-off"></a>복수 적용을 설정 및 해제하려면

1.  **도구** 메뉴에서 **옵션**을 클릭합니다.

2.  에 **옵션** 대화 상자에서 **Database**합니다.

    > [!NOTE]
    >  선택 **모든 설정 표시** 경우는 **Database** 노드가 표시 되지 않습니다.

3.  클릭 **O/R 디자이너**합니다.

4.  설정 **복수 이름 적용** 에 **Enabled** = **False** 설정 하는 **O/R 디자이너** 클래스 이름은 변경 되지 않습니다 있도록 .

5.  설정 **복수 이름 적용** 에 **Enabled** = **True** 추가 된 개체의 클래스 이름에 복수형 규칙을 적용할 수는 **O/R 디자이너**합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)