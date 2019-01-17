---
title: 인코딩할 URI에 잘못 된 문자가 | Microsoft 문서
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
- VS.WebClient.Help.SCRIPT5024
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e93d145ea6b0991123c2a7c80f8acf54a83a264
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349792"
---
# <a name="the-uri-to-be-encoded-contains-an-invalid-character"></a>인코딩될 URI에 잘못된 문자가 있습니다.
문자열로 URI (일정 한 리소스 식별자)로 인코딩 하려고 하지만 잘못 된 문자가 포함 되어 있어. 대부분의 문자는 Uri로 변환 된 문자열 내에 유효한, 일부 유니코드 문자 시퀀스를 사용할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   인코딩될 문자열에 올바른 유니코드 문자열만 있는지 확인 합니다. 완전 한 URI 구성 요소 및 구분 기호 구성 됩니다. 꺾쇠 괄호의 이름은 구성 요소를 나타내며와 ":", "/", ";" 및 "?" 예약 된 문자를 구분 기호로 사용 됩니다. 일반 형식은 다음과 같습니다.  
  
    ```JavaScript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent 함수](../../javascript/reference/encodeuricomponent-function-javascript.md)