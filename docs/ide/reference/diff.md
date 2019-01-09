---
title: -Diff
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf58c25611fd52c6e8db8e8210101e1c80153275
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53844540"
---
# <a name="diff"></a>/Diff
두 파일을 비교합니다. 차이점은 특별한 Visual Studio 창에 표시됩니다.

## <a name="syntax"></a>구문

```cmd
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]
```

## <a name="arguments"></a>인수
 `SourceFile`

 필수 요소. 비교할 첫 번째 파일의 전체 경로와 이름입니다.

 `TargetFile`

 필수 요소. 비교할 두 번째 파일의 전체 경로와 이름입니다.

 `SourceDisplayName`

 선택 사항입니다. 첫 번째 파일의 표시 이름입니다.

 `TargetDisplayName`

 선택 사항입니다. 두 번째 파일의 표시 이름입니다.