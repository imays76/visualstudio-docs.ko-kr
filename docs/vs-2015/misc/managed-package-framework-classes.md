---
title: 관리 되는 패키지 프레임 워크 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed package framework, helper classes
- managed package helper classes
- Visual Studio SDK, managed package helper classes
- classes [Visual Studio SDK], managed package framework
ms.assetid: 15aedcc3-c79a-460b-b620-43223f1ae81e
caps.latest.revision: 24
manager: douge
ms.openlocfilehash: 38f159df52c99554ed931269f29ad57e72745b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556196"
---
# <a name="managed-package-framework-classes"></a>관리되는 패키지 프레임워크 클래스
MPF(관리되는 패키지 프레임워크) 클래스를 사용하여 관리 코드를 사용하는 Vspackage를 만들 수 있습니다. 이 클래스는 많은 VSPackage 인터페이스에 대한 기본 구현을 제공합니다. 구현 세부 정보 및 복잡성을 숨겨 MPF 만들 수 있게 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 최소량의 코드를 사용 하 여 통합 제품입니다.  
  
> [!WARNING]
>  관리되는 패키지 프레임워크 클래스를 포함하는 어셈블리는 대부분 Visual Studio SDK와 함께 제공됩니다. [프로젝트에 대한 관리되는 패키지 프레임워크](http://mpfproj11.codeplex.com/)에서 프로젝트에 대한 관리되는 패키지 프레임워크용 소스 코드를 다운로드할 수 있습니다.  
  
## <a name="mpf-namespaces"></a>MPF 네임스페이스  
 다음 표에서 MPF 네임 스페이스에서 제공 된 [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)]합니다.  
  
|네임스페이스|목차|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio>|COM 오류를 처리 하기 위한 유용한 클래스가 포함 되어 있습니다 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 상수 및 Win32 windows.|  
|<xref:Microsoft.VisualStudio.Package>|관리 코드 래퍼에 대 한 포함 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로젝트, 편집기 및 MSBuild.|  
|<xref:Microsoft.VisualStudio.Shell>|일반적인 Visual Studio의 여러 개체의 구현을 파생할 수 있는 MPF 기본 클래스를 포함합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Design>|포함 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 디자이너 확장 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization>|포함 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] serialization 디자이너 확장 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization.CodeDom>|포함 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] CodeDom 디자이너 확장 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Flavor>|프로젝트 하위 형식("버전")을 지원합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage 및 관리 패키지 프레임 워크](../misc/vspackages-and-the-managed-package-framework.md)   
 [Visual Studio Interop 어셈블리를 사용 하 여](../extensibility/internals/using-visual-studio-interop-assemblies.md)   
 [VSPackage 및 관리 패키지 프레임워크](../misc/vspackages-and-the-managed-package-framework.md)