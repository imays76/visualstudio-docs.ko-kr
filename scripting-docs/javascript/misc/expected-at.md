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
ms.openlocfilehash: 73e7e8fb43bb45e4c97b6bb5ec6c739c16a4423a
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349860"
---
# <a name="expected-"></a>'@'가 필요합니다.
사용 하 여 조건부 컴파일 문에서 사용할 변수를 만들려고 합니다 `@set` 문을 배치 하지 않고 있지만 at 기호 "**@**" 변수 이름 앞입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   추가 at 기호 "**@**" 변수 이름 바로 앞입니다. 예를 들어:  
  
    ```JavaScript  
    @set @myvar = 1  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [@set Statement](../../javascript/reference/at-set-statement-javascript.md)   
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)