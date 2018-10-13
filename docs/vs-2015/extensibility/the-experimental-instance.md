---
title: 실험적 인스턴스에서 | Microsoft Docs
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
- experimental builds
- VSPackages, experimental builds
- VSIP, experimental builds
ms.assetid: ead0df4e-6f88-4b42-9297-581b7902f050
caps.latest.revision: 37
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 212fc490c26ab66284cf7bdfa4e51946c817266d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49220443"
---
# <a name="the-experimental-instance"></a>실험적 인스턴스
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 개발 환경에서 변경할 수는 테스트 되지 않은 응용 프로그램을 보호 하려면 VSSDK 실험 하는 데 사용할 수 있는 실험적 공간을 제공 합니다. 일반적으로 Visual Studio를 사용 하 여 새 응용 프로그램을 개발 하지만이 실험적 인스턴스를 사용 하 여 실행할 수 있습니다.  
  
 VSIX 패키지에 있는 모든 응용 프로그램 디버그 모드에서 Visual Studio 실험적 인스턴스를 시작 합니다.  
  
 특정 솔루션 외부 Visual Studio의 실험적 인스턴스를 시작 하려면 명령 창에서 다음 명령을 실행 합니다.  
  
 "*\<Visual studio 설치 경로 >* \Common7\IDE\devenv.exe" RootSuffix Exp  
  
> [!NOTE]
>  실험적 인스턴스를 레지스트리에 쓸 합니다 `<version number>Exp` 고 `<version number>Exp_Config` 노드. 예를 들어 Visual Studio 2015 실험적 레지스트리 영역에는  
>   
>  `HKCU\Software\Microsoft\VisualStudio\14.0Exp` 및 `HKCU\Software\Microsoft\VisualStudio\14.0Exp_Config`  
  
 이 개발 하는 동안 실험적 인스턴스에서 확장을 실행 하는 것이 좋습니다. 확장을 배포 하는 경우 개발 인스턴스에서 실행 됩니다. 응용 프로그램을 등록 하는 방법에 대 한 자세한 내용은 참조 하세요. [Vspackage 등록](../extensibility/internals/registering-vspackages.md)합니다.

