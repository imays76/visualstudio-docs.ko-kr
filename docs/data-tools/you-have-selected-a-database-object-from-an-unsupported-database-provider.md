---
title: 지원되지 않는 데이터베이스 공급자에서 데이터베이스 공급자를 선택했습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 4efaf92c9f4688d6870c1152be27eb4c8f4ed933
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53894443"
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>지원되지 않는 데이터베이스 공급자에서 데이터베이스 공급자를 선택했습니다.

합니다 **O/R 디자이너** 에.NET Framework Data Provider for SQL Server 지원 (<xref:System.Data.SqlClient>). **확인**을 클릭하고 지원되지 않은 데이터베이스 공급자의 개체를 사용하여 계속 작업을 할 수 있지만 런타임에 예상치 못한 동작이 발생할 수도 있습니다.

> [!NOTE]
> .NET Framework Data Provider for SQL Server를 사용하는 데이터 연결만 지원됩니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- **확인**을 클릭합니다.

   지원 되지 않는 데이터베이스 공급자를 사용 하는 연결에 매핑되는 엔터티 클래스 디자인을 계속할 수 있습니다. 지원되지 않는 데이터베이스 공급자를 사용하면 예상치 못한 동작이 발생할 수도 있습니다.

    또는

- 클릭 **취소**합니다.

   작업이 중지됩니다. .NET Framework Provider for SQL Server를 사용하는 데이터 연결을 만들거나 사용합니다.

## <a name="see-also"></a>참고 항목

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)