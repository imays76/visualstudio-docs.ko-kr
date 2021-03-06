---
title: ResourcesGenerator 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d2d470c91d6303976e5afcbffc7f4eff968ea04
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49173305"
---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> 작업은 하나 이상의 리소스(.jpg, .ico, .bmp, 이진 형식의 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 및 기타 확장 형식)를 .resources 파일에 포함합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`OutputPath`|필수 **String** 매개 변수입니다.<br /><br /> 출력 디렉터리의 경로를 지정합니다. 경로가 절대 경로가 아니면 루트 프로젝트 디렉터리의 상대 경로로 처리됩니다.|  
|`OutputResourcesFile`|필수 **ITaskItem** 출력 매개 변수입니다.<br /><br /> 생성된 .resources 파일의 경로 및 이름을 지정합니다. 경로가 절대 경로가 아니면 루트 프로젝트 디렉터리에 상대적으로 .resource 파일이 생성됩니다.|  
|`ResourcesFiles`|필수 **ITaskItem[]** 매개 변수입니다.<br /><br /> 생성된 .resources 파일에 포함할 하나 이상의 리소스를 지정합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 단일 .bmp 리소스로 .resources 파일을 생성합니다. .bmp 리소스는 프로젝트 루트 디렉터리에 상대적인 디렉터리에 생성됩니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>참고 항목  
 [WPF MSBuild 참조](../msbuild/wpf-msbuild-reference.md)   
 [작업 참조](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)   
 [WPF 응용 프로그램 빌드(WPF)](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)



