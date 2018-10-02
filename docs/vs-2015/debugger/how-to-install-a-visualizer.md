---
title: '방법: 시각화 도우미 설치 | Microsoft Docs'
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
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5152c47635f8ca2f2bb0a6a32c7767682006860a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564965"
---
# <a name="how-to-install-a-visualizer"></a>방법: 시각화 도우미 설치
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 시각화 도우미 설치](https://docs.microsoft.com/visualstudio/debugger/how-to-install-a-visualizer)합니다.  
  
시각화 도우미를 만든 후에는 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 사용할 수 있도록 이 시각화 도우미를 설치해야 합니다. 시각화 도우미를 설치하는 과정은 간단합니다.  
  
> [!NOTE]
>  **Store** 앱에만 표준 텍스트, HTML, XML 및 JSON 시각화 도우미는 지원 합니다. 사용자가 만든 사용자 지정 시각화 도우미는 지원되지 않습니다.  
  
### <a name="to-install-a-visualizer"></a>시각화 도우미를 설치하려면  
  
1.  빌드한 시각화 도우미가 들어 있는 DLL을 찾습니다.  
  
2.  이 DLL을 다음 위치 중 한 곳에 복사합니다.  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  원격 디버깅에 관리되는 시각화 도우미를 사용하려면 원격 컴퓨터의 동일한 경로에 DLL을 복사합니다.  
  
4.  디버깅 세션을 다시 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 시각화 도우미 만들기](../debugger/create-custom-visualizers-of-data.md)   
 [방법: 시각화 도우미 작성](../debugger/how-to-write-a-visualizer.md)



