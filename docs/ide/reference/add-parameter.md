---
title: 메서드 빠른 작업에 매개 변수 추가
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0337f9869764f544f5248d4da717af849457b8e8
ms.sourcegitcommit: 6672a1e9d135d7e5cca3cceea07c6fe5a0871475
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2018
ms.locfileid: "47443787"
---
# <a name="add-a-parameter-to-a-method-using-a-quick-action"></a>빠른 작업을 사용하여 메서드에 매개 변수 추가

이 코드 생성은 다음에 적용됩니다.

- C#

- Visual Basic

**대상:** 사용법을 기준으로 메서드에 매개 변수를 자동으로 추가할 수 있습니다.

**시기:** 메서드에 매개 변수를 추가해야 하며, 자동으로 메서드를 제대로 선언하려고 합니다.

**이유:** 호출 전에 메서드 선언에 매개 변수를 추가할 수 있지만, 이 기능은 메서드 호출을 기준으로 자동으로 추가합니다.

## <a name="how-to-use-it"></a>사용 방법

1. 메서드 호출에 여분의 인수를 추가합니다.

   빨간색의 “구불구불한 선”이 호출하는 메서드의 이름 아래에 나타납니다.

2. 빠른 작업 메뉴가 나타날 때까지 빨간색 “구불구불한 선”을 포인터로 가리킵니다. 빠른 작업 메뉴에서 **아래쪽 화살표**를 선택하고 **[메서드]에 매개 변수 추가**를 선택합니다.

   ![Visual Studio의 메서드에 매개 변수 추가 빠른 작업](media/add-parameter-to-method.png)

   > [!TIP]
   > 메서드 호출 줄에 커서를 놓은 다음, **Ctrl**+**.** 을 누르거나, 파일 여백에 있는 전구 아이콘을 선택하여 빠른 작업 메뉴에 액세스할 수도 있습니다.

   Visual Studio에서 메서드 선언에 새 매개 변수를 추가합니다.

> [!NOTE]
> 메서드에 대한 다른 호출이 있는 경우, 새로 추가된 매개 변수에 대한 인수를 지정하지 않기 때문에 이 빠른 작업을 사용한 후 오류가 발생할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [생성자에 매개 변수 추가](generate-constructor.md#addparameter)