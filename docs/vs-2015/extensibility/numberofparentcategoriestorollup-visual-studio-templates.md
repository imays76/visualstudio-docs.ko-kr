---
title: NumberOfParentCategoriesToRollUp (Visual Studio 템플릿) | Microsoft Docs
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
- http://schemas.microsoft.com/developer/vstemplate/2005#NumberOfParentCategoriesToRollUp
helpviewer_keywords:
- NumberOfParentCategoriesToRollUp element [Visual Studio Templates]
- <NumberOfParentCategoriesToRollUp> element [Visual Studio Templates]
ms.assetid: 6f9d36f5-ae23-4a92-8132-b11799e2c21a
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b0b766c9064f8a6f6f09036d602365d37a9174dc
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51769714"
---
# <a name="numberofparentcategoriestorollup-visual-studio-templates"></a>NumberOfParentCategoriesToRollUp(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

부모 범주에 템플릿 표시 하는 횟수를 지정 합니다 **새 프로젝트** 대화 상자.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<NumberOfParentCategoriesToRollUp >  
  
## <a name="syntax"></a>구문  
  
```  
<NumberOfParentCategoriesToRollUp>  
    1  
</NumberOfParentCategoriesToRollUp>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에서 템플릿이 표시되는 방식을 정의합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 `integer` 값이 필요 합니다.  
  
 이 값에서 템플릿을 표시 하는 부모 범주 수를 지정 합니다 **새 프로젝트** 대화 상자.  
  
## <a name="remarks"></a>설명  
 `NumberOfParentCategoriesToRollUp`는 선택적 요소입니다.  
  
## <a name="example"></a>예제  
 이 예제에 대 한 메타 데이터는 [!INCLUDE[csprcs](../includes/csprcs-md.md)] Windows 응용 프로그램입니다. 이 메타 데이터를 사용 하 여 템플릿 최상위 수준 아래 두 수준 폴더에 배치 되 [!INCLUDE[csprcs](../includes/csprcs-md.md)] 노드를 서식 파일에서 최상위 노드에 나타납니다 합니다 **새 프로젝트** 대화 상자. 경우는 `NumberOfParentCategoriesToRollUp` 템플릿을 나타나는 노드는에서 실제로 설정 하지 않으면.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <NumberOfParentCategoriesToRollUp>2</NumberOfParentCategoriesToRollUp>  
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

