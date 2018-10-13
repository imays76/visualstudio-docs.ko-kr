---
title: -SafeMode(devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b785a3e43726522f6e6cc6ce99dec4bf3815c81d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230082"
---
# <a name="safemode-devenvexe"></a>/SafeMode(devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
안전 모드에서 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]을(를) 시작하고 기본 환경 및 서비스만 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>설명  
 이 스위치는 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]이(가) 시작될 때 모든 타사 VSPackages의 로드를 차단하므로 안정적으로 실행되도록 합니다.  
  
## <a name="description"></a>설명  
 다음 예제에서는 안전 모드에서 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]을(를) 시작합니다.  
  
## <a name="code"></a>코드  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)



