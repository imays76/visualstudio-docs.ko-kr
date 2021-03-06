---
title: Assembly 요소 (Visual Studio 템플릿 마법사 확장명) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Assembly
helpviewer_keywords:
- Assembly element [Visual Studio Template Wizard Extension]
- <Assembly> element [Visual Studio Template Wizard Extension]
ms.assetid: 0c3dc280-1753-4ea2-a13c-d31d13b935b2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 07b01c993bb9a20dcb836a67bc2a9e8d78135adb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53828188"
---
# <a name="assembly-element-visual-studio-template-wizard-extension"></a>Assembly 요소 (Visual Studio 템플릿 마법사 확장명)
이름 또는 구현 하는 어셈블리의 강력한 이름을 지정 합니다 `IWizard` 인터페이스입니다.  
  
 \<VSTemplate>  
\<WizardExtension >  
\<어셈블리 >  
  
## <a name="syntax"></a>구문  
  
```  
<Assembly>AssemblyName</Assembly>  
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
|[WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)|템플릿 마법사를 사용자 지정에 대 한 등록 요소를 포함 합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 구현 하는 어셈블리를 지정 하는이 텍스트는 `IWizard` 인터페이스입니다. 전체 어셈블리 이름으로이 어셈블리 이름을 지정 해야 합니다. 예를 들어, `MyAssembly, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11dd0a3a, Custom = null`을 입력합니다.  
  
## <a name="remarks"></a>설명  
 `Assembly`은 `WizardExtension`의 필수 자식 요소입니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 표준 프로젝트 템플릿에 대 한 메타 데이터는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows 응용 프로그램입니다.  
  
```xml
<VSTemplate Version="3.0.0" Type="Item"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyTemplate</Name>  
        <Description>Template using IWizard extension</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs</ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
    <WizardExtension>  
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11dd0a3a, Custom=null</Assembly>  
        <FullClassName>MyWizard.CustomWizard</FullClassName>  
    </WizardExtension>  
</VSTemplate>  
```
  
## <a name="see-also"></a>참고 항목

- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [프로젝트 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)
- [방법: 프로젝트 템플릿에 마법사 사용](../extensibility/how-to-use-wizards-with-project-templates.md)