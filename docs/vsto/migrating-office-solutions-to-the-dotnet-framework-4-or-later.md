---
title: .NET Framework 4 이상으로 Office 솔루션 마이그레이션
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Project.TargetFrameworkWarning
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 88f417ef8835e0614a2bf13b3717f19e3718feaf
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53845128"
---
# <a name="migrate-office-solutions-to-the-net-framework-4-or-later"></a>.NET Framework 4 이상으로 Office 솔루션 마이그레이션
  Office 프로젝트의 대상 프레임 워크를 변경 된 경우는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 나중에.NET Framework의 이전 버전에서 몇 가지 추가 단계가 필요할 계속 개발 및 최종 사용자 컴퓨터에서 솔루션을 실행 합니다. 자세한 내용은 [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Office 프로젝트를 실행 하는 변경 필요한](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.  
  
 또한 프로젝트가 더 이상 컴파일되지 않을 수 있습니다. Office 프로젝트의 일부 기능은 각 버전의 .NET Framework에 대해 다른 프로그래밍 모델을 사용합니다. Office 프로젝트의 대상 프레임워크가 이전 버전의 .NET Framework에서 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상으로 변경된 경우 프로젝트의 코드를 다음과 같이 변경해야 합니다.  
  
- [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Excel 및 Word 프로젝트 업데이트](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
- [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Office 프로젝트에서 리본 사용자 지정 업데이트](/visualstudio/vsto/update-ribbon-customizations-in-office-projects-to-migrate-to-dotnet-framework-4-or-4-5)  
  
- [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Outlook 프로젝트에서 양식 영역 업데이트](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
  이전 버전의 Visual Studio에서 해당 프로젝트를 업그레이드하는 경우 Office 프로젝트의 대상 프레임워크가 변경됩니다. 자세한 내용은 [업그레이드 및 Office 솔루션 마이그레이션](../vsto/upgrading-and-migrating-office-solutions.md)합니다.  
  
  이유에 대 한 자세한 내용은 일부 Office 프로젝트의 기능이 다른 프로그래밍 모델을 대상으로 할 때 합니다 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상 [.NETFramework4.5또는.NETFramework4를대상으로하는Office프로젝트의디자인변경](../vsto/changes-to-the-design-of-office-projects-that-target-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md) 하 고 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)합니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션을 만들고 디자인](../vsto/designing-and-creating-office-solutions.md)   
 [방법: .NET Framework의 버전 대상](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [Office 솔루션의 오류 문제 해결](../vsto/troubleshooting-errors-in-office-solutions.md)   
 [Office 솔루션 오류에에서 대 한 추가 지원](../vsto/additional-support-for-errors-in-office-solutions.md)  
