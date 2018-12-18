---
title: -ResetSkipPkgs(devenv.exe) | Microsoft Docs
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
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2345c675f55be5c01ea65f5266d4b73bff30feed
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49190374"
---
# <a name="resetskippkgs-devenvexe"></a>/ResetSkipPkgs(devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
모든 옵션의 선택을 취소하여 VSPackages 로딩 문제를 방지하기 위해 사용자가 VSPackages에 추가된 로딩을 건너뛴 다음 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]를 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Devenv /ResetSkipPkgs  
```  
  
## <a name="remarks"></a>설명  
 SkipLoading 태그가 존재하면 VSPackage를 로드할 수 없습니다. 해당 태그를 지우면 VSPackage를 다시 로드할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 모든 SkipLoading 태그를 지웁니다.  
  
```  
Devenv.exe /ResetSkipPkgs  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)



