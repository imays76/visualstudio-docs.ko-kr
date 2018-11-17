---
title: CaptureCurrentFrame | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76dca819f6a6a236f3b0e206dd0585cebce3f25e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51764427"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

그래픽 로그 파일에 현재 프레임의 나머지 부분을 캡처합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>설명  
 다른 캡처가 현재 진행 중인 경우(예: `BeginCapture` 함수에 의해 시작된 캡처) 해당 캡처를 완료하고 그래픽 로그에 다른 프레임으로 기록합니다. 이후에 즉시 그래픽 진단에서 다른 프레임으로도 기록되는 현재 프레임의 나머지 부분 캡처를 시작합니다. 현재 프레임의 끝은 호출로 표시됩니다.  
  
 프레임을 캡처하려면 캡처 그래픽 정보를 기록 하 고 앱을 준비 해야 합니다-즉, 호출 했어야 합니다 [Init](../debugger/init.md) 의 인스턴스를 통해 합니다 `VsgDbg` 클래스를 호출 하기 전에 `CaptureCurrentFrame`입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Init](../debugger/init.md)   
 [BeginCapture](../debugger/begincapture.md)



