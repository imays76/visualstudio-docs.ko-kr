---
title: 속성을 삭제할 수 없습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 7e85860de7494ae7d93ad37bd0a115fa786f0a87
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174015"
---
# <a name="the-property-property-name-cannot-be-deleted"></a>속성 \<속성 이름 >을 삭제할 수 없습니다

속성 \<속성 이름 >으로 설정 되어 있으므로 삭제할 수 없습니다 합니다 **Discriminator Property** 간 상속 \<클래스 이름 > 및 \<클래스 이름 >

선택한 속성이로 설정 되어는 **Discriminator Property** 오류 메시지에 표시 된 클래스 간 상속 합니다. 속성이 데이터 클래스 간 상속 구성에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.

설정 합니다 **Discriminator Property** desired 속성을 삭제할 수 있도록 데이터 클래스의 다른 속성에 있습니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 에 **O/R 디자이너**, 오류 메시지에 표시 된 데이터 클래스를 연결 하는 상속 선을 선택 합니다.

2. 설정 된 **판별자** 속성을 다른 속성입니다.

3. 속성 삭제를 다시 한 번 시도합니다.

## <a name="see-also"></a>참고자료

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)