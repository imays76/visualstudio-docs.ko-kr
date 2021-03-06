---
title: 배열 길이 유한한 양수로 할당 해야 | Microsoft 문서
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
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63a9d714173334192028b9096de41968befa85ef
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348700"
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>배열의 길이는 유한한 양수로 할당해야 합니다.
설정 하는 경우는 **길이** 기존 속성 **배열** 양의 정수 또는 0이 되지 않은 배열 길이 지정한 개체입니다. 에 값을 할당 하는 경우이 오류가 발생 합니다 **길이** 속성을는 `Array` 음수인 개체나 not-a-number (`NaN`). [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 전체 정수 소수를 자동으로 변환 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   Length 속성에 양의 정수를 할당 합니다. 최대 정수 값 (약 4 십억)이 아닌 배열의 크기에 대 한 상한 제한은 없습니다. 다음 예제에서는 설정 하는 올바른 방법은 합니다 **길이** 의 속성을 **배열** 개체.  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)