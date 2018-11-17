---
title: 디렉터리에 추가 된 새 항목 추가 대화 상자 | Microsoft Docs
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
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d094f9911b80f3cff3e648da2593c62e0429fb54
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51751496"
---
# <a name="adding-directories-to-the-add-new-item-dialog-box"></a>새 항목 추가 대화 상자에 디렉터리 추가
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

다음 코드 예제에 대 한 디렉터리의 새 집합을 등록 하는 방법에 설명 합니다 **새 항목 추가** 대화 상자. 에 대 한 디렉터리를 **새 항목 추가** 대화 상자는 각 프로젝트에 대해 다릅니다. 따라서 디렉터리에 프로젝트 하위 키를 등록 된 \<HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects >:  
  
## <a name="the-registry-script"></a>레지스트리 스크립트  
  
```  
NoRemove Projects  
{  
  NoRemove %GUID_Project%  
  {  
    NoRemove AddItemTemplates  
    {  
      NoRemove TemplateDirs  
      {  
        ForceRemove %CLSID_Package%  
        {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
          {  
            val TemplatesDir = s '%Template_Path%'     
            val SortPriority = d 2000  
          }  
        }  
      }  
    }  
  }  
}  
```  
  
 Template_Path 값 프로젝트 템플릿이 포함 된 디렉터리의 전체 경로 지정 합니다. 이러한 템플릿은.vsz 파일 또는 정형화 된 템플릿 파일을 복제할 수 있습니다.  
  
 SortPriority 값 정렬 우선 순위를 지정합니다.  
  
## <a name="adding-items-to-an-existing-project"></a>기존 프로젝트에 항목 추가  
 기존 프로젝트에 항목을 추가할 수도 있습니다. 예를 들어, 한 [!INCLUDE[csprcs](../../includes/csprcs-md.md)] 프로젝트 항목을 추가할 수 있습니다는 \<루트 > \Program Files\Microsoft Visual Studio \VC#\CSharpProjectItems\LocalProjectItems 폴더. 이 경우에 `%GUID_Project%` C# 프로젝트 ({0} FAE04EC0-301F-11D3-BF4B-00C04F79EFBC})에 대 한 GUID입니다.  
  
 또한 프로젝트 하위 형식 프로그래밍 하 여 기존 프로젝트를 확장할 수 있습니다. 프로젝트 하위 형식을 사용 하 여 새 프로젝트 형식을 작성 하지 않고도 프로젝트를 확장할 수 있습니다. 프로젝트 하위 형식에 대 한 자세한 내용은 참조 하세요. [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [항목에 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [새 프로젝트 대화 상자에 디렉터리 추가](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)

