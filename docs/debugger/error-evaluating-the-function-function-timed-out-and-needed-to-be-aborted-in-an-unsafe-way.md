---
title: '오류: 함수를 계산 &#39;함수&#39; 시간이 초과 되어 안전 하지 않은 방식으로 중단 하는 데 필요한 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.unsafe_func_eval_abort
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a72bd821d7ecd32e82b2ad3b02debe03ff511531
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53883313"
---
# <a name="error-evaluating-the-function-39function39-timed-out-and-needed-to-be-aborted-in-an-unsafe-way"></a>오류: 함수를 계산 &#39;함수&#39; 시간이 초과 되어 안전 하지 않은 방식으로 중단 하는 데 필요한

전체 메시지 텍스트: ‘function’ 함수를 계산하는 중 시간이 초과되어 안전하지 않은 방식으로 중단해야 했습니다. 대상 프로세스를 손상 있을 수 있습니다. 

디버거는 쉽게.NET 개체의 상태를 검사 추가 코드 (일반적으로 속성 getter 메서드 및 ToString 함수)를 실행 하는 디버깅된 프로세스를 자동으로 실행 됩니다. 대부분의 모든 시나리오에서 이러한 함수는 신속 하 게 완료 하 고 디버깅을 훨씬 쉽게 확인 합니다. 그러나 디버거 샌드박스에서 응용 프로그램을 실행 하지 않습니다. 결과적으로, 속성 getter 또는 중단 된 네이티브 함수를 호출 하는 ToString 메서드를 복구할 수 없는 긴 시간 제한이 발생할 수 있습니다. 이 오류 메시지에서 발견 되 면이 발생 했습니다.
 
이 문제에 대 한 한 가지 이유 디버거 속성으로 계산 되 면 수 있다는 점입니다만 실행 검사 중인 스레드입니다. 따라서 디버깅된 응용 프로그램 내에서 실행 되도록 다른 스레드에서 속성 기다리고 및.NET 런타임을 중단할 수 없는 방식으로 대기 중인 경우이 문제가 발생 합니다.
 
## <a name="to-correct-this-error"></a>이 오류를 해결하려면
 
이 문제에 일부의 솔루션이 있습니다.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>솔루션 1 ToString 메서드나 속성 getter 호출에서 디버거를 방지
 
오류 메시지에는 디버거를 호출 하려고 하는 함수의 이름을 알려줍니다. 이 함수를 수정할 수 있는 경우 속성 getter 또는 ToString 메서드 호출에서 디버거를 방지할 수 있습니다. 다음 중 하나를 시도 합니다.
 
* 메서드는 속성 getter 외에도 코드의 다른 유형으로 변경 하거나 ToString 메서드 및 문제가 사라집니다.
    또는
* (예: ToString) 형식에서 DebuggerDisplay 특성을 정의 하 고 ToString 이외의 평가 디버거를 사용할 수 있습니다.
    또는
* (예: 속성 getter) 배치는 `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` 속성에는 특성입니다. 이 API 호환성을 위해 속성을 유지 해야 하는 메서드가 있는 경우에 유용할 수 있습니다 하지만 실제로 메서드 여야 합니다.
 
### <a name="solution-2-have-the-target-code-ask-the-debugger-to-abort-the-evaluation"></a>솔루션 2 평가 중단 하도록 디버거에 요청 대상 코드
 
오류 메시지에는 디버거를 호출 하려고 하는 함수의 이름을 알려줍니다. 속성 getter 또는 ToString 메서드를 제대로 실행 되도록 하려면 경우에 따라 실패, 특히 문제가 되는 환경에서에서 코드는 다른 스레드가 코드를 실행 하려면 필요한 경우 구현 함수를 호출할 수 `System.Diagnostics.Debugger.NotifyOfCrossThreadDependency` 함수를 중단 하도록 디버거에 요청 평가 합니다. 이 솔루션을 사용 하 여 여전히 명시적으로 이러한 함수를 평가할 수이 하 이지만 기본 동작은 NotifyOfCrossThreadDependency 호출이 발생 하는 경우 실행이 중지 되는 키를 누릅니다.
 
### <a name="solution-3-disable-all-implicit-evaluation"></a>솔루션 3 모든 암시적 평가 사용 하지 않도록 설정
 
이전 해결 방법이 문제를 해결 하지 하는 경우 이동할 **도구** > **옵션**, 설정의 선택을 취소 **디버깅**  >   **일반적인** > **속성 확인 및 기타 암시적 함수 호출**합니다. 대부분의 암시적 함수 실행이 비활성화 됩니다 하 고 문제를 해결 해야 합니다.

### <a name="solution-4-enable-managed-compatibility-mode"></a>'{0}' 솔루션 관리 되는 호환성 모드를 사용 하도록 설정

레거시 디버깅 엔진으로 전환 하면이 오류를 제거할 수 있습니다. 로 이동 **도구** > **옵션**에서 설정을 선택 하 고 **디버깅** > **일반**  >  **사용 하 여 관리 되는 호환성 모드**합니다. 자세한 내용은 [디버깅 옵션 일반](../debugger/general-debugging-options-dialog-box.md)합니다.
