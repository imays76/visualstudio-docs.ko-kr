---
title: WaitStart | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e1e452fb46af37778a94dee271adf47a1255e1b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553176"
---
# <a name="waitstart"></a>WaitStart
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [WaitStart](https://docs.microsoft.com/visualstudio/profiling/waitstart)합니다.  
  
WaitStart 옵션을 사용하면 VSPerfCmd.exe Start 하위 명령이 프로파일러가 초기화되었거나 지정된 시간(초)이 경과되었을 때만 결과를 반환합니다. 기본적으로 Start 명령은 즉시 결과를 반환합니다. 프로파일러를 초기화하지 않고 Start 하위 명령이 반환되면 오류가 반환됩니다. 시간(초)을 지정하지 않으면 Start 명령은 무기한 대기합니다.  
  
 WaitStart 옵션은 프로파일러가 초기화되었는지 보장하기 위한 배치 파일에서 유용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Seconds`  
 Start 하위 명령에서 반환되기 전에 대기할 시간(초)입니다.  
  
## <a name="required-options"></a>필수 옵션  
 WaitStart 옵션은 Start 하위 명령과만 함께 사용할 수 있습니다.  
  
 **Output:** `filename`  
 출력 파일 이름을 지정합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 이 배치 파일 예제에서 Start 명령은 프로파일러가 초기화될 때까지 5초 동안 대기합니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```



