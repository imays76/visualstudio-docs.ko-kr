---
title: 응용 프로그램 리소스 관리(.NET) | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- editors [Visual Studio], Resource Designer
- Resource Designer
- resources [Visual Studio], managing
- Resources page in Project Designer
- resources types, Resource Designer
- application resources [Visual Studio]
- Project Designer, Resources page
ms.assetid: f2582734-8ada-4baa-8a7c-e2ef943ddf7e
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 487da2a484c49e265306c26d881a2fffc7608002
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543278"
---
# <a name="managing-application-resources-net"></a>응용 프로그램 리소스 관리(.NET)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

리소스 파일은 응용 프로그램의 일부이지만 컴파일되지 않는 파일입니다(예: 아이콘 파일 또는 오디오 파일). 이러한 파일은 컴파일 프로세스에 포함되지 않으므로 이진 파일을 다시 컴파일할 필요 없이 변경할 수 있습니다. 응용 프로그램을 지역화할 계획인 경우 모든 문자열 및 응용 프로그램을 지역화할 때 변경해야 하는 다른 리소스에 대해 리소스 파일을 사용해야 합니다.  
  
 .NET 데스크톱 앱의 리소스에 대한 자세한 내용은 [데스크톱 앱의 리소스](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)를 참조하세요. C++ 데스크톱 앱의 리소스에 대한 자세한 내용은 [Working with Resource Files](http://msdn.microsoft.com/library/2699a539-b369-4b78-80f0-df03eb7b6780)을 참조하세요.  
  
 Windows 스토어 앱은 데스크톱 앱과 다른 리소스 모델을 사용합니다. Windows 스토어 앱의 리소스에 대한 자세한 내용은 Windows 개발자 센터 웹 사이트에서 [응용 프로그램 리소스 정의](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx) 를 참조하세요.  
  
## <a name="working-with-resources"></a>리소스 작업  
 관리 코드 프로젝트에서 프로젝트 속성 창을 엽니다( **솔루션 탐색기** 에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택하거나, **빠른 실행** 창에서 **프로젝트 속성** 을 입력하거나, **솔루션 탐색기** 창에서 Alt+Enter 입력). **리소스** 탭을 선택합니다. 프로젝트에 .resx 파일이 포함되지 않은 경우 하나를 추가하고, 다른 종류의 리소스를 추가 및 삭제하고, 기존 리소스를 수정할 수 있습니다.  
  
 C++ 프로젝트의 리소스를 사용하는 방법을 알아보려면 [방법: 리소스 만들기](http://msdn.microsoft.com/library/aad44914-9145-45a3-a7d8-9de89b366716)를 참조하세요.

