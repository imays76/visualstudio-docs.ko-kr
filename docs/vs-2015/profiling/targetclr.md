---
title: TargetCLR | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 915ca4a859b4c80f785262f1c05698c4d34a683b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542980"
---
# <a name="targetclr"></a>TargetCLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [TargetCLR](https://docs.microsoft.com/visualstudio/profiling/targetclr)합니다.  
  
**TargetCLR** 옵션은 한 응용 프로그램에 두 개 이상의 CLR 버전이 로드된 경우 프로파일링할 CLR(공용 언어 런타임) 버전을 지정합니다.  
  
 기본적으로 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로파일링 도구는 응용 프로그램에서 로드된 CLR의 첫 번째 버전을 대상으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>매개 변수  
 `ClrVersion`  
 CLR의 버전 번호입니다. 버전 형식 **vN.N.NNNNN**을 사용합니다.  
  
## <a name="required-options"></a>필수 옵션  
 **TargetCLR** 옵션은 **Launch** 또는 **Attach** 옵션에만 사용할 수 있습니다.  
  
 **Launch:** `AppName`  
 지정한 응용 프로그램을 시작하고 프로파일링을 시작합니다.  
  
 **Attach:** `PID`  
 지정된 프로세스 프로파일링을 시작합니다.  
  
## <a name="example"></a>예제  
 이 예제에서 TargetCLR 옵션은 CLR 버전 4.0.11003이 프로파일링되고 있는지 확인하는 데 사용됩니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```



