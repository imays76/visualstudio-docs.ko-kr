---
title: Folder 요소 (Visual Studio 프로젝트 템플릿) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Folder
helpviewer_keywords:
- Folder element [Visual Studio project templates]
ms.assetid: 558e3d41-0db5-4c44-82bb-6bb87892b093
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aacda209865ee9e7d9eae48a93be7e23f16c26ec
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53912732"
---
# <a name="folder-element-visual-studio-project-templates"></a>Folder 요소 (Visual Studio 프로젝트 템플릿)
프로젝트에 추가 될 폴더를 지정 합니다.  
  
 \<VSTemplate>  
 \<TemplateContent >  
 \<Project>  
 \<폴더 >  
  
## <a name="syntax"></a>구문  
  
```  
<Folder Name="Project Folder">  
    <Folder> ... </Folder>  
    <ProjectItem> ... </ProjectItem>  
</Folder>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수 특성입니다.<br /><br /> 프로젝트 폴더의 이름입니다.|  
|`TargetFolderName`|선택적 특성입니다.<br /><br /> 폴더에 지정할 프로젝트를 템플릿에서 만들면 이름을 지정 합니다. 이 특성은 매개 변수 대체를 사용 하 여 폴더 이름을 만드는 데 유용 또는 국제 문자열을 사용 하 여 폴더 이름이 사용할 수 없습니다에서 직접 합니다 *.zip* 파일입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`Folder`|프로젝트에 추가할 폴더를 지정 합니다. `Folder` 요소에는 자식 포함 될 수 있습니다 `Folder` 요소입니다.|  
|[프로젝트 항목](../extensibility/projectitem-element-visual-studio-item-templates.md)|프로젝트에 추가할 파일을 지정 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[프로젝트](../extensibility/project-element-visual-studio-templates.md)|선택적 자식 요소 [TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)합니다.|  
  
## <a name="remarks"></a>설명  
 `Folder` 선택적 자식이 `Project`합니다.  
  
 템플릿에서 폴더에 프로젝트 항목을 구성 하려면 다음 방법 중 하나를 사용할 수 있습니다.  
  
-   템플릿에서 폴더를 포함 *.zip* 파일과 프로젝트에 추가 합니다 *.vstemplate* 파일에서 파일의 경로를 지정 하 여는 `ProjectItem` 요소를 사용 하 여 `Folder` 요소. 이것이 권장된 방법입니다. 예:  
  
     `...`  
  
     `<ProjectItem>\Folder\item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   템플릿에서 폴더를 포함 *.zip* 파일과 프로젝트에 추가 합니다 *.vstemplate* 파일 `Folder` 요소입니다. 예:  
  
     `...`  
  
     `<Folder name="Folder">`  
  
     `<ProjectItem>item.cs</ProjectItem>`  
  
     `</Folder>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   템플릿에서 폴더를 포함 하지 *.zip* 파일을 사용 하 여 폴더를 추가 하지만 합니다 `TargetFileName` 특성을 `ProjectItem` 요소입니다. 예:  
  
     `...`  
  
     `<ProjectItem TargetFileName="\Folder\item.cs">item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
## <a name="example"></a>예제  
 다음 예제에서는 프로젝트 템플릿에 대 한 메타 데이터는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows 응용 프로그램입니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <Folder Name="Properties">  
                <ProjectItem>AssemblyInfo.cs</ProjectItem>  
                <ProjectItem>Resources.resx</ProjectItem>  
                <ProjectItem>Resources.Designer.cs</ProjectItem>  
                <ProjectItem>Settings.settings</ProjectItem>  
                <ProjectItem>Settings.Designer.cs</ProjectItem>  
            </Folder>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>참고자료  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)   
 [ProjectItem 요소(Visual Studio 항목 템플릿)](../extensibility/projectitem-element-visual-studio-item-templates.md)