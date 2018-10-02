---
title: 프로파일링 도구 명령줄 도구의 경로 지정 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ccf7739a8efacacec3c48b47a59d6db6f6e8de8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543833"
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>프로파일링 도구 명령줄 도구의 경로 지정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [프로 파일링 도구 명령줄 도구의 경로 지정](https://docs.microsoft.com/visualstudio/profiling/specifying-the-path-to-profiling-tools-command-line-tools)합니다.  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로파일링 도구 명령줄 도구의 경로가 PATH 환경 변수에 추가되지 않았습니다. 32비트 컴퓨터에는 도구가 단일 디렉터리에 있습니다. 64비트 컴퓨터에는 프로파일링 도구가 32비트 및 64비트 버전으로 있습니다.  
  
## <a name="32-bit-computers"></a>32비트 컴퓨터  
 32비트 컴퓨터에서 기본 프로파일러 도구가 위치한 디렉터리는 *드라이브*\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools입니다.  
  
## <a name="64-bit-computers"></a>64비트 컴퓨터  
 64비트 컴퓨터에서 프로파일링된 응용 프로그램의 대상 플랫폼에 따라 경로를 지정합니다.  
  
-   32비트 응용 프로그램의 경우 기본 프로파일러 도구 디렉터리는 다음과 같습니다.  
  
     *드라이브*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools  
  
-   64비트 응용 프로그램의 경우 기본 프로파일러 도구가 위치한 디렉터리는 다음과 같습니다.  
  
     *드라이브*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\x64



