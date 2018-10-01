---
title: '관리 디버깅: 권장 속성 설정 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], managed
- debugging managed code, recommended property settings
ms.assetid: 3d14a8d4-2925-44d0-be41-ec546d411db9
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50fa9b61d017be3e860c10f11688bcd79f252969
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542926"
---
# <a name="managed-debugging-recommended-property-settings"></a>관리되는 디버깅: 권장 속성 설정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [관리 디버깅: 권장 속성 설정](https://docs.microsoft.com/visualstudio/debugger/managed-debugging-recommended-property-settings)합니다.  
  
일부 속성은 모든 관리되는 디버깅 시나리오에서 동일한 방식으로 설정해야 합니다.  
  
 다음 표에는 권장 속성 설정이 나와 있습니다.  
  
 여기에 나와 있지 않은 설정은 관리되는 프로젝트의 형식에 따라 서로 다를 수 있습니다. 예를 들어 **시작 작업** 보다 Windows Forms 프로젝트를 다르게 설정 됩니다는 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 프로젝트입니다.  
  
### <a name="configuration-properties-on-the-build-c-or-compile-visual-basic-tab"></a>빌드(C#) 또는 컴파일(Visual Basic) 탭의 구성 속성  
  
|**속성 이름**|**설정**|  
|-----------------------|-----------------|  
|**DEBUG 상수 정의**|C# 및 F#: 확인란을 선택합니다. 이렇게 하면 응용 프로그램에서 Debug 클래스를 사용할 수 있습니다.|  
|**TRACE 상수 정의**|C# 및 F#: 확인란을 선택합니다. 이렇게 하면 응용 프로그램에서 Trace 클래스를 사용할 수 있습니다.|  
|**코드 최적화**|C#, F# 및 Visual Basic: false로 설정합니다. 코드를 최적화하면, 생성되는 명령이 소스 코드에 직접 대응되지 않기 때문에 디버깅하기 어렵습니다. 에이 설정을 선택할 수 있지만 코드에 표시 된 프로그램에 최적화 된 코드에만 나타나는 버그가 있다면 합니다 **디스어셈블리** 창 코드에 표시 되는 내용 일치 하지 않는 최적화 된 소스에서 생성 됩니다 편집기입니다. 최적화 된 코드를 디버깅 하려면 꺼야 [Just My Code](just-my-code.md)합니다.<br /><br /> 자세한 내용은 [C# 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-csharp-debug-configurations.md) 또는 [Visual Basic 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)합니다.|  
|**출력 경로**|Bin\Debug로\\합니다.|  
|**고급 컴파일 옵션**|Visual Basic만 클릭 **고급** 다음 표에 설명 된 고급 속성을 설정 하려면.|  
  
### <a name="advanced-compiler-settings-dialog-box"></a>고급 컴파일러 설정 대화 상자  
  
|**속성 이름**|**설정**|  
|-----------------------|-----------------|  
|**최적화 사용**|에 지정 된 이유로 false로 설정 합니다 **코드를 최적화** 앞의 표에 있는 옵션입니다.|  
|**디버깅 정보 생성**|이 확인란을 선택하면 컴파일 시 /DEBUG 플래그가 설정됩니다. 이렇게 하면 디버깅을 진행하는 데 필요한 정보가 생성됩니다.|  
|**DEBUG 상수 정의**|`DEBUG` 상수를 정의하려면 이 확인란을 선택합니다. 이렇게 하면 응용 프로그램에 <xref:System.Diagnostics.Debug> 클래스를 사용할 수 있습니다.|  
|**TRACE 상수 정의**|`TRACE` 상수를 정의하려면 이 확인란을 선택합니다. 이렇게 하면 응용 프로그램에 <xref:System.Diagnostics.Trace> 클래스를 사용할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [C#, F#, and Visual Basic Project Types](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)(C#, F# 및 Visual Basic 프로젝트 형식)



