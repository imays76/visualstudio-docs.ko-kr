---
title: Choose 요소(MSBuild) | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#Choose
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Choose> Element [MSBuild]
- Choose Element [MSBuild]
ms.assetid: 7b8b025a-d944-4f5c-9018-c89fc2ef146d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dbb67391a2dcb3aea15eca2b06d52664ea8cebf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554378"
---
# <a name="choose-element-msbuild"></a>Choose 요소(MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Choose 요소 (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/choose-element-msbuild)합니다.  
  
  
자식 요소를 평가하여 평가할 `ItemGroup` 요소 및/또는 `PropertyGroup` 요소의 집합 하나를 선택합니다.  
  
 \<Project>  
 \<Choose>  
 \<When>  
 \<Choose>  
 ...  
 \<Otherwise>  
 \<Choose>  
 ...  
  
## <a name="syntax"></a>구문  
  
```  
<Choose>  
    <When Condition="'StringA'=='StringB'">... </When>  
    <Otherwise>... </Otherwise>  
</Choose>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Otherwise](../msbuild/otherwise-element-msbuild.md)|선택적 요소입니다.<br /><br /> 모든 `When` 요소의 조건이 `false`로 평가될 경우 평가할 코드 `PropertyGroup` 및 `ItemGroup` 요소의 블록을 지정합니다. `Choose` 요소에 0개 이상의 `Otherwise` 요소가 있을 수 있으며 마지막 요소여야 합니다.|  
|[When](../msbuild/when-element-msbuild.md)|필수적 요소입니다.<br /><br /> `Choose` 요소에서 선택할 수 있는 가능한 코드 블록을 지정합니다. `Choose` 요소에는 `When` 요소가 하나 이상 있을 수 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Otherwise](../msbuild/otherwise-element-msbuild.md)|모든 `When` 요소가 `false`로 평가될 경우 실행할 코드 블록을 지정합니다.|  
|[Project](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 프로젝트 파일의 필수 루트 요소입니다.|  
|[When](../msbuild/when-element-msbuild.md)|`Choose` 요소에서 선택할 수 있는 가능한 코드 블록을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `Choose`, `When` 및 `Otherwise` 요소는 몇 가지 가능한 대안 중에서 실행할 코드의 한 섹션을 선택하는 방법을 제공하기 위해 함께 사용됩니다. 자세한 내용은 [조건부 구문](../msbuild/msbuild-conditional-constructs.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 프로젝트에서는 `Choose` 요소를 사용하여 설정할 `When` 요소의 속성 값 집합을 선택합니다. 두 `When` 요소의 `Condition` 특성이 모두 `false`로 평가되면 `Otherwise` 요소의 속성 값이 설정됩니다.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition="'$(Configuration)' == ''">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='debug' ">  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <DebugType>full</DebugType>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\Debug\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
            <ItemGroup>  
                <Compile Include="UnitTesting\*.cs" />  
                <Reference Include="NUnit.dll" />  
            </ItemGroup>  
        </When>  
        <When Condition=" '$(Configuration)'=='retail' ">  
            <PropertyGroup>  
                <DebugSymbols>false</DebugSymbols>  
                <Optimize>true</Optimize>  
                <OutputPath>.\bin\Release\</OutputPath>  
                <DefineConstants>TRACE</DefineConstants>  
            </PropertyGroup>  
        </When>  
        <Otherwise>  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\$(Configuration)\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
        </Otherwise>  
    </Choose>  
    <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
</Project>  
```  
  
## <a name="see-also"></a>참고 항목  
 [조건부 구문](../msbuild/msbuild-conditional-constructs.md)   
 [프로젝트 파일 스키마 참조](../msbuild/msbuild-project-file-schema-reference.md)


