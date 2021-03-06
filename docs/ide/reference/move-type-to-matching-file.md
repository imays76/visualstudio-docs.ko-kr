---
title: 형식을 일치하는 파일 리팩터링으로 이동
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 793ae8f86bf4c4641a3170cde011a3912d0d38ef
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53870549"
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>형식을 일치하는 파일 리팩터링으로 이동

이 리팩터링은 다음에 적용됩니다.

- C#

- Visual Basic

**내용:** 선택한 형식을 같은 이름을 가진 별도의 파일로 이동할 수 있습니다.

**시기:** 동일한 파일에 구분하려는 여러 클래스, 구조체, 인터페이스 등이 있습니다.

**이유:** 같은 파일에 여러 형식을 넣으면 이러한 형식을 찾기 어려울 수 있습니다. 형식을 같은 이름을 가진 파일로 이동하면 코드를 더 쉽게 읽고 탐색할 수 있습니다.

## <a name="how-to"></a>방법

1. 커서를 정의된 형식의 이름 안에 놓습니다. 예:

   ```csharp
   class Person
   ```

   ```vb
   Class Person
   ```

2. 다음 작업 중 하나를 수행합니다.

   - 줄의 임의 위치에서 **Ctrl**+**.** 를 눌러
   - 형식 이름을 마우스 오른쪽 단추로 클릭하고 **빠른 작업 및 리팩터링**을 선택합니다.

1. 메뉴에서 **형식을 *TypeName*.cs로 이동**을 선택합니다. 여기서 *TypeName*은 선택한 형식의 이름입니다.

   형식과 동일한 이름을 가진 프로젝트의 새 파일로 형식이 이동됩니다.

   - C#: 

      ![인라인 결과 - C#](media/movetype-result-cs.png)

   - Visual Basic:

      ![인라인 결과 - Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
