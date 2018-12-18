---
title: '보안 경고: 신뢰할 수 없는 사용자가 소유한 프로세스에 연결하면 위험할 수 있습니다. 다음 정보가 의심 스 럽 또는 확실 하지 않은 경우이 프로세스에 연결 하지 않는 | Microsoft Docs'
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
- vs.debug.attachsecuritywarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dac3ad5d51e2934bd2cbdf5a8fe9ad30a4a90a8b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51745580"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>보안 경고: 신뢰할 수 없는 사용자가 소유한 프로세스에 연결하면 위험할 수 있습니다. 아래의 정보가 의심스럽거나 잘 모르겠으면 이 프로세스에 연결하지 마세요.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 경고 대화 상자는 부분적으로 신뢰할 수 있는 코드가 포함되어 있거나 신뢰할 수 없는 사용자가 소유한 프로세스에 연결할 때 연결이 실행되기 바로 전에 표시됩니다. 악의적인 코드가 포함된 신뢰할 수 없는 프로세스는 디버깅을 수행하는 컴퓨터에 손상을 줄 수 있습니다. 프로세스 이유가 있는 경우 클릭 해야 **취소** 디버깅을 중지 합니다.  
  
 정상적인 시나리오를 디버깅 하는 경우에이 경고를 표시 하지 않으려면, Visual Studio를 닫고이 레지스트리 키의 값을 1로 설정: `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`, 한 다음 Visual Studio를 다시 시작 합니다. 시나리오의 디버깅을 마친 후 이 값을 0으로 다시 설정하고 Visual Studio를 다시 시작합니다.  
  
 "신뢰할 수 있는 사용자"에는 사용자 자신을 비롯하여 `aspnet`, `localsystem`, `networkservice` 및 `localservice`와 같은 .NET Framework가 설치된 컴퓨터에 일반적으로 정의되어 있는 표준 사용자 집합도 포함됩니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 이름  
 디버깅하도록 요청된 어셈블리의 이름입니다.  
  
 사용자  
 현재 사용자입니다.  
  
 연결  
 연결하여 계속 디버깅합니다.  
  
 연결 안 함  
 프로세스에 연결하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [디버거 보안](../debugger/debugger-security.md)



