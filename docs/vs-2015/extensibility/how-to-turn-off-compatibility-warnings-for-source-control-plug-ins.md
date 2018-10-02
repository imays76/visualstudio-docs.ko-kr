---
title: '방법: 소스 제어 플러그 인에 대 한 호환성 경고 해제 | Microsoft Docs'
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
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
caps.latest.revision: 22
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5cfa9ed4b06f8a2f567f6446f85f35e3f0cde244
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553111"
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>방법: 소스 제어 플러그 인에 대 한 호환성 경고 해제
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [소스 제어 플러그 인에 대 한 경고 하는 호환성 설정 해제](https://docs.microsoft.com/visualstudio/extensibility/how-to-turn-off-compatibility-warnings-for-source-control-plug-ins)합니다.  
  
사용자의 소스 제어를 적용 하는 경우 몇 가지 호환성 경고가 표시 될 수 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]입니다. 경고 표시를 소스 제어 플러그 인의 기능에 따라 달라 집니다 있으며 자세한 다음과 같이 해제할 수 있습니다.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>경고를 사용 하지 않도록 설정: "Visual Studio...를 사용 하 여 최적의 소스 제어 통합 되도록"  
  
-   다음 레지스트리 항목 (필요한 경우 값 추가)를 설정 합니다.  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = dword: 00000001  
  
     모든에 대해이 경고를 표시 하는 비-[!INCLUDE[vsvss](../includes/vsvss-md.md)] 플러그 인입니다.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>경고를 사용 하지 않도록 설정: "설치 된 원본 제어 공급자는 모든 기능...을 지원 하지 않습니다"  
  
-   (필요한 경우 값 추가)는 다음 두 레지스트리 값을 설정 합니다.  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider dword:00000000은 =  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = dword: 00000001  
  
     이 경고는 소스 제어 플러그 인을 지원 하지 않는 경우 명시적으로 재진입 여러 프로젝트에 대 한 (즉, 하는 경우 한 번에 하나의 파일 및 프로젝트에서 확인할 수)에 표시 됩니다.  
  
     재진입을 지원 하는 것이 좋습니다 (`SCC_CAP_REENTRANT` 기능);이 경고가 제거 됩니다. 그러나 이러한 지원이 가능 하지 않은 이러한 레지스트리 항목을 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기능 플래그](../extensibility/capability-flags.md)

