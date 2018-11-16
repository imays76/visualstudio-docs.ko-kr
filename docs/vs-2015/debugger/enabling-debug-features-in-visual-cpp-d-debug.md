---
title: Visual c + +에서 디버그 기능 활성화 (-/d_debug) | Microsoft Docs
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
helpviewer_keywords:
- /D_DEBUG compiler option [C++]
- debugging [C++], enabling debug features
- debugging [MFC], enabling debug features
- assertions, enabling debug features
- D_DEBUG compiler option
- MFC libraries, debug version
- debug builds, MFC
- _DEBUG macro
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf560bcde09b9d2e3c2bee689c92c9900c6e2af5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51760597"
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>Visual C++에서 디버그 기능 활성화(/D_DEBUG)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../includes/vcprvc-md.md)]을 어설션 기호를 사용 하 여 프로그램을 컴파일할 때 사용 하도록 설정 같은 디버깅 기능 **_DEBUG** 정의 합니다. 정의할 수 있습니다 **_DEBUG** 두 가지 방법 중 하나에서:  
  
- 지정할 **#define _DEBUG** 소스 코드에서 또는  
  
- 지정 된 **/D_DEBUG** 컴파일러 옵션입니다. (마법사를 사용 하 여 Visual Studio에서 프로젝트를 만들면 **/D_DEBUG** 디버그 구성에서 자동으로 정의 됩니다.)  
  
  때 **_DEBUG** 가 정의 컴파일러 코드 섹션을 컴파일합니다 **#ifdef _DEBUG** 고 `#endif`입니다.  
  
  MFC 프로그램의 디버그 구성은 MFC 라이브러리의 디버그 버전과 링크해야 합니다. MFC 헤더 파일을 정의 하면 같은 기호에 따라 올바른 버전의 MFC 라이브러리와 링크 하려면 결정 **_DEBUG** 하 고 **_UNICODE**합니다. 자세한 내용은 참조 하세요 [MFC 라이브러리 버전](http://msdn.microsoft.com/library/3d7a8ae1-e276-4cf8-ba63-360c2f85ad0e)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [C++ 디버그 구성에 대한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)



