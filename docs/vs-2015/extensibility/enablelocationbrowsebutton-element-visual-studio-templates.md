---
title: EnableLocationBrowseButton 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#EnableLocationBrowseButton
helpviewer_keywords:
- EnableLocationBrowseButton [Visual Studio project templates]
ms.assetid: a12d10d8-af49-482a-af77-e084fd07a47d
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 04d5710012840079e3381f09725b96b8f329872d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51795741"
---
# <a name="enablelocationbrowsebutton-element-visual-studio-templates"></a>EnableLocationBrowseButton 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

지정 여부를 합니다 **찾아보기** 단추를 사용할 수는 **새 프로젝트** 대화 상자에서 사용자가 새 프로젝트를 저장 된 기본 디렉터리를 쉽게 수정할 수 있도록 합니다.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<EnableLocationBrowseButton >  
  
## <a name="syntax"></a>구문  
  
```  
<EnableLocationBrowseButton> true/false </EnableLocationBrowseButton>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에서 템플릿이 표시되는 방식을 정의합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 텍스트 여야 `true` 또는 `false`를 표시할 것인지 여부를 나타내는 **찾아보기** 단추를 **새 프로젝트** 대화 상자.  
  
## <a name="remarks"></a>설명  
 `EnableLocationBrowseButton`는 선택적 요소입니다. 기본값은 `true`를 표시 합니다 **찾아보기** 단추를 **새 프로젝트** 대화 상자.  
  
 에 **새 프로젝트** 대화 상자에서를 **위치** 텍스트 상자가 새 프로젝트를 저장 된 디렉터리를 지정 합니다. 합니다 **찾아보기** 단추를 표시 하 여이 디렉터리를 수정할 수 있습니다 합니다 **프로젝트 위치** 컴퓨터에서 사용할 수 있는 다른 디렉터리에 쉽게 이동할 수 있는 대화 상자 및 그런 다음 새 프로젝트 저장 된 디렉터리를 선택 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 메타 데이터는 [!INCLUDE[csprcs](../includes/csprcs-md.md)] Windows 응용 프로그램입니다.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <EnableLocationBrowseButton>false</EnableLocationBrowseButton>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)

