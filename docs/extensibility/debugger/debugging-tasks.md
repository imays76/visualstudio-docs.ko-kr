---
title: 디버깅 작업 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aa719871e075a5448fa2d351c5bd7950a833601a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900154"
---
# <a name="debug-tasks"></a>작업 디버그
프로그램을 디버깅 하려면이 시작 해야 합니다 및는 디버그 엔진 (DE)에 연결 해야 합니다. 그렇지 않으면는 DE 이전에 시작된 된 프로그램에 연결 되어야 합니다. 연결 되 면는 DE 특정 시작 이벤트를 생성 해야 합니다. 응답으로 디버그 패키지는 IDE에서 설정 된 중단점은 바인딩 하려고 합니다. 프로그램에서 바인딩된 중단점에 도달 하면 중지 하 고 사용자 입력을 기다립니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [보안 문제](../../extensibility/debugger/security-issues.md)  
 프로그램을 디버깅 하는 데 필요한 보안 단계를 설명 합니다.  
  
 [프로그램 실행](../../extensibility/debugger/launching-a-program.md)  
 프로그램을 시작 하려면 운영 체제를 호출 하는 DE를 지정 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [프로그램에 직접 연결](../../extensibility/debugger/attaching-directly-to-a-program.md)  
 이미 실행 중인 프로세스에서 프로그램을 디버깅 하는 데 사용 하는 프로세스를 설명 합니다.  
  
 [시작 후 시작 이벤트 보내기](../../extensibility/debugger/sending-startup-events-after-a-launch.md)  
 프로그램의 주 진입점은 고 디버깅 준비 될 때까지 DE 프로그램에 연결 되 면 발생 하는 이벤트를 나열 합니다.  
  
 [실행 제어](../../extensibility/debugger/control-of-execution.md)  
 DE 일반적으로 보내는 방법을 진입점 이벤트, 부하 완료 이벤트를 또는 상황에 따라 중지 이벤트를 설명 합니다.  
  
 [중단점 바인딩](../../extensibility/debugger/binding-breakpoints.md)  
 하는 방법을 설명, 중단점을 설정 하는 사용자를 하는 경우 IDE 요청에서 중단점을 만들려고 하면 디버그 세션의 메시지를 표시 합니다.  
  
 [식 평가](../../extensibility/debugger/evaluating-expressions.md)  
 식 생성 방법 및 식이 계산 되는 경우를 설명 합니다.  
  
 [시각화 및 데이터 보기](../../extensibility/debugger/visualizing-and-viewing-data.md)  
 식 계산기 (EE)에 의해 형식 시각화 도우미 및 사용자 지정 뷰어 지 원하는 방법을 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 기본 디버깅 아키텍처 개념을 설명합니다.  
  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)  
 Visual Studio 디버깅 구성 요소, DE, EE, 및 기호 처리기 (SH) 포함 하는 개요를 제공 합니다.  
  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 DE 동시에 코드, 설명서 및 식 평가 컨텍스트 내에서 작동 하는 방법을 설명 합니다. 세 개의 컨텍스트, 위치, 위치 또는 평가를 관련 각각에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)