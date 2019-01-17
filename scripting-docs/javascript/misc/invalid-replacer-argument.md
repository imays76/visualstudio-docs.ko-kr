---
title: 잘못 된 치환 인수가 | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4727186f-facd-4aa6-9447-bbefbae83f07
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f144e733bf115cc98bf61b23a2ed3e4e3cda1e0
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346217"
---
# <a name="invalid-replacer-argument"></a>치환 인수가 잘못되었습니다.
호출 하려고 `JSON.stringify` 잘못 된 인수를 사용 합니다. `replacer` 인수는 함수 또는 배열 이어야 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   변경 된 `replacer` 함수 또는 배열 인수입니다.  
  
## <a name="example"></a>예제  
 이 예제의 코드에 런타임 오류가 발생 하기 때문에 `memberfilter` 은 함수 또는 배열 대신 개체입니다.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Object();  
  
// This line will cause a runtime error.  
var jsontext = JSON.stringify(contact, memberfilter, "\t");  
```  
  
## <a name="see-also"></a>참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)