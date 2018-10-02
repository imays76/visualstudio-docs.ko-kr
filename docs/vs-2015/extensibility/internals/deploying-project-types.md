---
title: 프로젝트 형식 배포 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 66069ac71fbe59e8b63126d66d2a0cc63ed095bc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551038"
---
# <a name="deploying-project-types"></a>프로젝트 형식 배포
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [프로젝트 형식 배포](https://docs.microsoft.com/visualstudio/extensibility/internals/deploying-project-types)합니다.  
  
[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] 새 프로젝트 형식 aggregator (ProjectAggregator2.dll) 및 재배포 (ProjectAggregator2.msi)에 대 한 Windows Installer 패키지를 설치합니다. 관리 코드 프로젝트 형식에 대해 새 집계가 사용 해야 합니다. ProjectAggregator2 작동 방법 제한 된 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] aggregator 관리 코드 프로젝트 형식을 올바르게 작동 하지 못하도록 하는 프로젝트입니다. 다음 단계를 새 집계를 사용 하 여 VSPackage를 변경 하는 방법에 설명 합니다.  
  
1.  솔루션에서 NativeHierarchyWrapper 프로젝트를 제거 합니다.  
  
2.  설치 프로그램에서 NativeHierarchyWrapper 이진 파일을 제거 합니다.  
  
3.  ProjectAggregator2.msi 설치에 추가 합니다.

