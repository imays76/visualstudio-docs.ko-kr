---
title: GetFrameworkSdkPath 작업 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3e35cac8399ab97ae3825e35de5b249db7e23a7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541713"
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [GetFrameworkSdkPath 작업](https://docs.microsoft.com/visualstudio/msbuild/getframeworksdkpath-task)합니다.  
  
  
[!INCLUDE[winsdklong](../includes/winsdklong-md.md)]에 대한 경로를 검색합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
 다음 표에서는 `GetFrameworkSdkPath` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|선택적 `String` 읽기 전용 출력 매개 변수입니다.<br /><br /> .NET SDK 버전 2.0에 대한 경로가 있는 경우 반환합니다. 그렇지 않으면 `String.Empty`를 반환합니다.|  
|`FrameworkSdkVersion35Path`|선택적 `String` 읽기 전용 출력 매개 변수입니다.<br /><br /> .NET SDK 버전 3.5에 대한 경로가 있는 경우 반환합니다. 그렇지 않으면 `String.Empty`를 반환합니다.|  
|`FrameworkSdkVersion40Path`|선택적 `String` 읽기 전용 출력 매개 변수입니다.<br /><br /> .NET SDK 버전 4.0에 대한 경로가 있는 경우 반환합니다. 그렇지 않으면 `String.Empty`를 반환합니다.|  
|`Path`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 버전이 있는 경우 최신 .NET SDK에 대한 경로를 포함합니다. 그렇지 않으면 `String.Empty`를 반환합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `GetFrameworkSdkPath` 작업을 사용하여 `SdkPath` 속성에서 [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)]에 대한 경로를 저장합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkSdkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="SdkPath" />  
        </GetFrameworkSdkPath>  
        <Message Text="$(SdkPath)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)


