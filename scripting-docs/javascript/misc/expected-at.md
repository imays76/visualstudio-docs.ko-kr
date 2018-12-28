---
title: 예상 ' @' | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1032
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 82ff8b74-1710-4358-9a26-dc92ab29c53b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 191402a9ba265e5acfb15d1931e260f6b366687e
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804554"
---
# <a name="expected-"></a>'@'가 필요합니다.
사용 하 여 조건부 컴파일 문에서 사용할 변수를 만들려고 합니다 `@set` 문을 배치 하지 않고 있지만 at 기호 "**@**" 변수 이름 앞입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   추가 at 기호 "**@**" 변수 이름 바로 앞입니다. 다음은 사용 예를 보여줍니다.  
  
    ```JavaScript  
    @set @myvar = 1  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [@set 문](../../javascript/reference/at-set-statement-javascript.md)   
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)