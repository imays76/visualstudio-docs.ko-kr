---
title: VS 셸 배포
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 61cf6e716f082abf28043d56d1a8803853d894aa
ms.sourcegitcommit: ef828606e9758c7a42a2f0f777c57b2d39041ac3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39566675"
---
# <a name="vs-shell-deployment"></a>VS 셸 배포

Visual Studio를 확인할 수는 격리 된 셸 있습니다 도메인 특정 언어 및 해당 솔루션 표시 방법을 상호 작용 해야 하는 기능입니다. Visual Studio 격리 셸에 대 한 자세한 내용은 참조 하세요. [격리 셸 사용자 지정](../extensibility/customizing-the-isolated-shell.md)합니다.

## <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>배포 대상으로 한 Visual Studio Shell을 설정 하려면

1.  에 **DslPackage** 프로젝트를 열고 **source.extension.tt**합니다.

2.  아래 `<SupportedProducts>` 삽입:

    ```xml
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
    ```

     바꿉니다 *MyIsolatedShell* 격리 셸 패키지의 이름입니다.