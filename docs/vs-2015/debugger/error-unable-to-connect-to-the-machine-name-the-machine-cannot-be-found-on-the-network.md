---
title: '오류: 컴퓨터에 연결할 수 없습니다 &lt;이름을&gt;입니다. 네트워크에서 컴퓨터를 찾을 수 없습니다. | Microsoft 문서'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
ms.assetid: b584b5db-ef52-45ed-8561-1314da3cc5b8
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8660b08adb0d925eb0f1b084673877734a47207
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733767"
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>오류: 컴퓨터에 연결할 수 없습니다 &lt;이름을&gt;입니다. 네트워크에서 컴퓨터를 찾을 수 없습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 오류는 다음과 같은 경우에 발생합니다.  
  
-   원격 컴퓨터에 대한 연결이 끊어진 경우  
  
-   원격 컴퓨터의 사용자 계정이 비활성화된 경우  
  
-   원격 컴퓨터의 암호가 만료된 경우  
  
### <a name="to-resolve-this-behavior"></a>이 동작을 해결하려면  
  
-   로컬 컴퓨터와 원격 컴퓨터가 동일한 네트워크에 있는지 확인합니다. 이를 확인하려면 Microsoft Windows 탐색기(또는 파일 탐색기)를 사용하여 원격 컴퓨터에 액세스해 봅니다.  
  
     — 및 —  
  
-   원격 컴퓨터에 연결하는 데 사용 중인 사용자 계정이 활성화되어 있는지 확인합니다.  
  
     — 및 —  
  
-   원격 컴퓨터에 연결하는 데 사용 중인 암호가 유효하고 만료되지 않았는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [장치에서 원격 도구 설정](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)



