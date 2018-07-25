---
title: 속성은 연결에 참여 하 고 있으므로 삭제할 수 없습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 6ed6b14f64d16d1f18d4b358761169c3d424cee8
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174064"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>속성 &lt;속성 이름이&gt; 연결에 참여 하 고 있으므로 삭제할 수 없습니다 &lt;연결 이름&gt;

선택한 속성이로 설정 되어는 **연결 속성** 클래스 간의 연결에 대 한 오류 메시지에 표시 합니다. 속성이 데이터 클래스 간 연결에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.

설정 된 **연결 속성** desired 속성을 삭제할 수 있도록 데이터 클래스의 다른 속성에 있습니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 연결 선을 선택 합니다 **O/R 디자이너** 오류 메시지에 표시 된 데이터 클래스를 연결 하는 합니다.

2. 열려는 줄을 두 번 클릭 합니다 **연결 편집기** 대화 상자.

3. 속성을 제거 합니다 **연결 속성**합니다.

4. 속성 삭제를 다시 한 번 시도합니다.

## <a name="see-also"></a>참고자료

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)