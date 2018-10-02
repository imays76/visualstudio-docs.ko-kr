---
title: -Setup (devenv.exe) | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75b7fb7d812135014a8b868ef7590c99e83c15b5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553890"
---
# <a name="setup-devenvexe"></a>/Setup(devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [-설치 프로그램 (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/setup-devenv-exe)합니다.  
  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 가 모든 사용 가능한 VSPackages에서 메뉴, 도구 모음 및 명령 그룹을 설명하는 리소스 메타데이터를 병합하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /setup  
```  
  
## <a name="remarks"></a>설명  
 이 스위치는 인수가 필요 없습니다. `devenv /setup` 명령은 일반적으로 설치 프로세스의 마지막 단계로 표시됩니다. `/setup` 스위치의 사용이 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]를 시작하지는 않습니다.  
  
 `devenv` 및 [devenv](../../ide/reference/setup-devenv-exe.md) 스위치를 사용하려면 관리자 권한으로 [devenv](../../ide/reference/installvstemplates-devenv-exe.md) 를 실행해야 합니다.  
  
## <a name="example"></a>예제  
 이 예는 VSPackages를 포함하는 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 버전의 설치에서 마지막 단계를 보여 줍니다.  
  
```  
devenv /setup  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)



