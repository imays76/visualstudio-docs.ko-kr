---
title: 프로젝트 항목에는 특성을 추가 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [Visual Studio], adding to a project item
ms.assetid: 404a71d5-cce5-44e7-9eaf-d747c794fedb
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3c5e1cba339ab89957a942968acbb88f2204a6af
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49907861"
---
# <a name="adding-an-attribute-to-a-project-item"></a>프로젝트 항목에 특성 추가
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetItemAttribute%2A> 고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> 가져오기 및 프로젝트 항목의 특성 값을 설정 합니다. SetItemAttribute 만듭니다 특성 아직 존재 하지 않는 경우 프로젝트 항목 메타 데이터를 추가 합니다.  
  
## <a name="adding-an-attribute-to-a-project-item"></a>프로젝트 항목에 특성 추가  
  
#### <a name="to-add-an-attribute-to-a-project-item"></a>프로젝트 항목에 특성을 추가 하려면  
  
-   다음 코드에서는 합니다 <xref:EnvDTE.DTE> 자동화 개체 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> 프로젝트 항목에 특성을 추가 하는 방법입니다. 프로젝트 항목 이름 "program.cs"에서 프로젝트 항목 ID는 가져옵니다. 특성 "MyAttribute"이 프로젝트 항목에 추가 되 고 "MyValue" 값을 지정 합니다.  
  
    ```  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution =     (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath =         (string)project.ProjectItems.Item("Program.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(  
            itemId, "MyAttribute", "MyValue");  
    }  
  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 프로젝트 파일의 데이터 유지](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)

