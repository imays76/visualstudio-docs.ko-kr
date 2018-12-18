---
title: 코드 조각
description: Mac용 Visual Studio에서 코드 조각을 사용하여 효율적으로 프로그래밍하는 방법
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 0FE27C0C-A861-4133-A74E-8D0505CF5342
ms.openlocfilehash: a2db4477b0258159c867aa1219f858040d2efb26
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51295374"
---
# <a name="code-snippets"></a>코드 조각

 _코드 템플릿_이라고도 하는 코드 조각은 미리 작성된 코드 블록을 삽입하고 편집할 수 있으므로 프로그래밍의 능률을 높이는 데 유용합니다. 코드 조각을 사용하면 공통 패턴을 빠르게 추가하거나 개발자가 구문을 잘 모르는 경우 새로운 패턴을 배우는 데도 편리합니다. C#, F#, HTML, XML, Python 및 Razor용 템플릿이 제공됩니다.

이 섹션에서는 코드 조각을 만들고, 삽입하고, 사용하는 방법을 설명합니다.

## <a name="inserting-a-snippet"></a>코드 조각 삽입

다양한 방법으로 코드 조각을 추가할 수 있으며, 아래에서는 그중 일부를 설명합니다.

* **탭 확장** - 템플릿 이름을 입력하여 목록에서 해당 이름을 선택하고 **탭** 및 **탭** 키를 눌러 이를 추가합니다.

  ![코드의 탭 확장](media/source-editor-image13.png)

* **도구 상자** - 도구 상자 패드를 사용하여 모든 코드 조각의 목록을 표시합니다. 도구 상자의 템플릿을 소스 코드에서 올바른 위치에 끌어 놓습니다.

  ![도구 상자의 코드 조각](media/source-editor-image14.png)

* **템플릿 삽입 명령** - 현재는 템플릿 삽입 기능에 설정된 기본 키 바인딩이 없습니다. 키 바인딩을 만들려면 **Visual Studio > 기본 설정 > 키 바인딩**으로 이동하고 `template`을 검색합니다. 이렇게 하면 [바인딩 편집] 필드에 원하는 키 바인딩을 추가한 다음,  **적용**을 클릭할 수 있습니다.

  ![템플릿 삽입 명령](media/source-editor-image15.png)

## <a name="creating-a-new-template"></a>새 템플릿 만들기

다양한 언어로 작성된 수많은 기존 템플릿을 사용하고 편집할 수 있지만, **Visual Studio > 기본 설정 > 텍스트 편집기 > 코드 조각**으로 이동하여 새 템플릿을 추가할 수도 있습니다.

![새 템플릿 삽입](media/source-editor-image12.png)

## <a name="see-also"></a>참고 항목

* [코드 조각(Windows의 Visual Studio)](/visualstudio/ide/code-snippets)