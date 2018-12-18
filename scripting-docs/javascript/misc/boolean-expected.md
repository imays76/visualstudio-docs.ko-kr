---
title: 부울이 필요 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5010
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb8ec8f7244b98cfa628794b485859dbec611c19
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868094"
---
# <a name="boolean-expected"></a>부울이 필요합니다.
호출 하려고 합니다 **Boolean.prototype.toString** 또는 **Boolean.prototype.valueOf** 이외의 다른 형식의 개체의 메서드를 `Boolean`입니다. 이 형식의 호출 개체 유형 이어야 `Boolean`합니다. 예를 들어:

```JavaScript
var o = new Object;
o.f = Boolean.prototype.toString;
o.f();
```

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 만 호출 합니다 **Boolean.prototype.toString** 또는 **Boolean.prototype.valueOf** 형식의 개체에 있는 메서드의 **부울입니다.**

## <a name="see-also"></a>참고 항목

- [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)
- [데이터 형식](../../javascript/data-types-javascript.md)
- [프로그램 흐름 제어](../../javascript/controlling-program-flow-javascript.md)
- [데이터 복사, 전달 및 비교](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)