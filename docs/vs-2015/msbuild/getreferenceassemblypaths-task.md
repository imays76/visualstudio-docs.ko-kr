---
title: GetReferenceAssemblyPaths 작업 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 619a533e1bdbdec00e631aac64d6ddf84bf161c6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543142"
---
# <a name="getreferenceassemblypaths-task"></a>GetReferenceAssemblyPaths 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [GetReferenceAssemblyPaths 작업](https://docs.microsoft.com/visualstudio/msbuild/getreferenceassemblypaths-task)합니다.  
  
  
다양한 프레임워크의 참조 어셈블리 경로를 반환합니다.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 `GetReferenceAssemblyPaths` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ReferenceAssemblyPaths`|선택적 `String[]` 출력 매개 변수입니다.<br /><br /> `TargetFrameworkMoniker` 매개 변수를 기반으로 경로를 반환합니다. `TargetFrameworkMoniker`가 null이거나 비어 있으면 이 경로는 `String.Empty`가 됩니다.|  
|`FullFrameworkReferenceAssemblyPaths`|선택적 `String[]` 출력 매개 변수입니다.<br /><br /> 모니커의 프로필 부분을 고려하지 않고 `TargetFrameworkMoniker` 매개 변수를 기반으로 경로를 반환합니다. `TargetFrameworkMoniker`가 null이거나 비어 있으면 이 경로는 `String.Empty`가 됩니다.|  
|`TargetFrameworkMoniker`|선택적 `String` 매개 변수입니다.<br /><br /> 참조 어셈블리 경로와 연결된 대상 프레임워크 모니커를 지정합니다.|  
|`RootPath`|선택적 `String` 매개 변수입니다.<br /><br /> 참조 어셈블리 경로를 생성하는 데 사용할 루트 경로를 지정합니다.|  
|`BypassFrameworkInstallChecks`|선택 사항 [부울] (<!-- TODO: review code entity reference <xref:assetId:///Boolean?qualifyHint=False&amp;autoUpgrade=True>  -->) 매개 변수입니다.<br /><br /> `true`인 경우 대상 프레임워크에 따라 특정 런타임 프레임워크가 설치되었는지 확인하기 위해 기본적으로 `GetReferenceAssemblyPaths`가 수행하는 기본 검사를 무시합니다.|  
|`TargetFrameworkMonikerDisplayName`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 대상 프레임워크 모니커의 표시 이름을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 표에 나열된 매개 변수 외에, <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)


