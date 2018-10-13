---
title: 패키지를 디버그 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 61df51b422660a5ea116f136b0d5183e59293a02
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49286327"
---
# <a name="debug-package"></a>패키지 디버그
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

디버그 패키지는 Visual Studio shell에서 실행 하 고 전체 UI를 처리 합니다. Visual Studio 디버깅 인터페이스를 사용 하 고 세션 디버그 관리자 SDM ()를 사용 하 여 통신 합니다.  
  
 SDM을 통해 전송 되는 중단 이벤트 실행된 모드에서 디버거가 중단 모드 체인이 끊어진 프로그램에 포커스를 전환 합니다. 디버그 패키지가 이벤트에 의해 전송 되는 정보에서 스택 프레임 및 스레드를 추적 합니다.  
  
 디버그 패키지에 언어 또는 런타임 환경 종속성 없습니다. 구현 하거나 디버그 패키지를 수정할 필요는 없습니다.  
  
 디버그 패키지가 vsdebug.dll에 의해 구현 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [세션 디버그 관리자](../../extensibility/debugger/session-debug-manager.md)   
 [스택 프레임](../../extensibility/debugger/stack-frames.md)   
 [스레드](../../extensibility/debugger/threads.md)   
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)

