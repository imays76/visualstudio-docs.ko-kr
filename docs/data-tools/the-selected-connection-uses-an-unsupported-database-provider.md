---
title: 선택한 연결에서 지원되지 않는 데이터베이스 공급자를 사용합니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: cc74cea11e4c173a11f781af4ee78bf047353c53
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53932066"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>선택한 연결에서 지원되지 않는 데이터베이스 공급자를 사용합니다.

이 메시지는.NET Framework Data Provider for SQL Server에서 사용 하지 않는 항목을 끌어 오면 나타납니다 **서버 탐색기** 또는 **데이터베이스 탐색기** 에 [시각적 개체에 LINQ to SQL 도구 Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)합니다.

합니다 **O/R 디자이너** .NET Framework Provider for SQL Server를 사용 하는 데이터 연결만 지원 합니다. Microsoft SQL Server 또는 Microsoft SQL Server 데이터베이스 파일에 대한 연결만 유효합니다.

이 오류를 해결 하려면 SQL Server에 대 한.NET Framework Data Provider를 사용 하는 데이터 연결의 항목만 추가 합니다 **O/R 디자이너**합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Data.SqlClient>
- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
