---
title: 중단 모드 단계별 실행 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4fff7edc494c763407c65785fe1de0b3fd77d7b2
ms.sourcegitcommit: 8d38d5d2f2b75fc1563952c0d6de0fe43af12766
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39276509"
---
# <a name="stepping-in-break-mode"></a>중단 모드 단계별 실행
다음 섹션에서는 디버거가 중단 모드 이며 코드를 단계별로 실행 해야 하는 경우 발생 하는 프로세스를 설명 합니다.  
  
## <a name="stepping-process"></a>단계별 프로세스  
  
1.  호출 [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) 사용 하 여 [STEPKIND](../../extensibility/debugger/reference/stepkind.md) 하 고 [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) 단계의 실행에 대 한 인수입니다.  
  
2.  단계가 완료 되 면 송신을 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 중지 이벤트입니다.  
  
## <a name="see-also"></a>참고자료  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)