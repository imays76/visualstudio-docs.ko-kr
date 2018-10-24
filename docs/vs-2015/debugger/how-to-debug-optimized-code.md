---
title: '방법: 최적화 된 코드 디버깅 | Microsoft Docs'
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
- vs.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- breakpoints, in optimized code
- debugging [C++], optimized code
- optimization, debug builds
- debug builds, optimizing
- optimized code, debugging
ms.assetid: fc8eeeb8-6629-4c9b-99f7-2016aee81dff
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30d2b52de1d6341c333d52c96df83ee36802324f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49904611"
---
# <a name="how-to-debug-optimized-code"></a>방법: 최적화된 코드 디버깅
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

참고]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
> [!NOTE]
>  합니다 [/Zo (최적화 된 디버깅 향상)](http://msdn.microsoft.com/library/eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f)컴파일러 옵션 (Visual Studio 업데이트 3에 도입 됨)에 최적화 된 코드에 대 한 다양 한 디버깅 정보 생성 (으로 빌드하지 않은 프로젝트는 **/Od** 컴파일러 옵션입니다. 참조 [/O 옵션 (코드 최적화)](http://msdn.microsoft.com/library/77997af9-5555-4b3d-aa57-6615b27d4d5d)). 여기에는 지역 변수 및 인라인된 함수 디버깅에 대한 향상된 지원이 포함됩니다.  
>   
>  [편집 하며 계속 하기](../debugger/edit-and-continue-visual-csharp.md) 사용 하지 않으면 경우는 **/Zo** 컴파일러 옵션을 사용 합니다.  
  
 컴파일러는 코드를 최적화할 때 명령의 위치를 변경하고 재구성하여 더욱 효율적으로 코드를 컴파일합니다. 이렇게 컴파일러가 코드를 다시 정렬하기 때문에 디버거가 명령 집합에 해당하는 소스 코드를 항상 식별할 수 있는 것은 아닙니다.  
  
 최적화는 다음 항목에 영향을 미칠 수 있습니다.  
  
- 지역 변수. 최적화 프로그램에 의해 제거되거나 디버거에서 인식하지 못하는 위치로 이동할 수 있습니다.  
  
- 함수 내 위치. 최적화 프로그램에서 코드 블록을 병합할 때 변경됩니다.  
  
- 호출 스택 프레임의 함수 이름. 최적화 프로그램에서 두 함수를 병합할 때 문제가 발생할 수 있습니다.  
  
  모든 프레임에 대한 기호가 있음을 전제로, 호출 스택에 표시되는 프레임은 거의 아무 문제가 없습니다. 스택이 손상되거나 함수가 어셈블리 언어로 작성되거나 운영 체제 프레임이 호출 스택의 기호와 일치하지 않는 경우 호출 스택의 프레임에 문제가 발생합니다.  
  
  전역 변수, 정적 변수 및 구조 레이아웃은 항상 올바르게 표시됩니다. 구조를 가리키는 포인터가 있고 포인터 값이 올바르면 구조의 모든 멤버 변수에 올바른 값이 표시됩니다.  
  
  따라서 가능하면 최적화되지 않은 프로그램 버전을 사용하여 디버깅해야 합니다. 기본적으로 최적화는 Visual C++ 프로그램의 디버그 구성에서 해제되고 릴리스 구성에서는 설정됩니다.  
  
  그러나 최적화된 프로그램 버전에서만 버그가 나타날 수도 있습니다. 이 경우에는 최적화된 코드를 디버깅해야 합니다.  
  
### <a name="to-turn-on-optimization-in-a-debug-build-configuration"></a>디버그 빌드 구성에서 최적화를 설정하려면  
  
1. 새 프로젝트를 만들 때는 `Win32 Debug` 대상을 선택합니다. 사용 된 `Win32``Debug` 프로그램이 완전히 디버그 되 고을 빌드할 준비가 될 때까지 대상는 `Win32 Release` 대상입니다. 컴파일러는 `Win32 Debug` 대상을 최적화하지 않습니다.  
  
2. 솔루션 탐색기에서 프로젝트를 선택합니다.  
  
3. 에 **뷰** 메뉴에서 클릭 **속성 페이지**합니다.  
  
4. 에 **속성 페이지** 대화 상자에서 `Debug` 에서 선택한를 **구성** 드롭 다운 목록.  
  
5. 왼쪽의 폴더 보기를 선택 합니다 **C/c + +** 폴더입니다.  
  
6. 아래는 **c + +** 폴더 `Optimization`합니다.  
  
7. 오른쪽의 속성 목록에서 `Optimization`을 찾습니다. 옆에 있는 설정은 `Disabled (` [/Od](http://msdn.microsoft.com/library/b1ac31b7-e086-4eeb-be5e-488f7513f5f5)`)`합니다. 다른 옵션 중 하나를 선택 (`Minimum Size``(`[/o1](http://msdn.microsoft.com/library/2d1423f5-53d9-44da-8908-b33a351656c2)`)`합니다 `Maximum Speed``(` [/o2](http://msdn.microsoft.com/library/2d1423f5-53d9-44da-8908-b33a351656c2)`)`하십시오 `Full Optimization``(` [/Ox](http://msdn.microsoft.com/library/3ad7c30b-c615-428c-b1d0-2e024f81c760) `)`, 또는 `Custom`).  
  
8. `Custom`에 대해 `Optimization` 옵션을 선택한 경우 속성 목록에 있는 다른 속성에도 옵션을 설정할 수 있습니다.  
  
9. 구성 속성, C/c + + 프로젝트 속성 페이지의 명령줄 노드를 선택 하 고 추가 `(` [/Zo](http://msdn.microsoft.com/library/eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f) `)` 하는 **추가 옵션** 입력란입니다.  
  
    > [!WARNING]
    >  `/Zo`를 사용하려면 Visual Studio 2013 업데이트 3 이상이 필요합니다.  
    >   
    >  추가 `/Zo` 없게 [편집 하며 계속 하기](../debugger/edit-and-continue-visual-csharp.md)합니다.  
  
   최적화 된 코드를 디버깅할 때 사용 합니다 **디스어셈블리** 창 어떤 명령이 실제로 생성 되 고 실행을 확인 합니다. 중단점을 설정할 때는 중단점이 명령과 함께 이동할 수도 있다는 것을 알아야 합니다. 예를 들어, 다음 코드를 고려하십시오.  
  
```  
for (x=0; x<10; x++)  
```  
  
 이 줄에 중단점을 설정할 경우, 중단점이 열 번 적중될 것으로 기대하겠지만 코드가 최적화되면 중단점은 한 번만 적중됩니다. 이는 첫 번째 명령에서 `x` 값을 0으로 설정하기 때문입니다. 컴파일러는 이 명령이 한 번만 수행되는 것으로 인식하여 루프 밖으로 명령을 이동합니다. 중단점도 함께 이동합니다. `x`를 비교하고 증가시키는 명령은 루프 내에 남아 있습니다. 볼 때 합니다 **디스어셈블리** 창 합니다 [단계 단위](http://msdn.microsoft.com/en-us/8791dac9-64d1-4bb9-b59e-8d59af1833f9) 명령으로 제어를 강화 최적화 된 코드를 단계별로 실행 하는 경우에 유용 하는 자동으로 설정 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)



