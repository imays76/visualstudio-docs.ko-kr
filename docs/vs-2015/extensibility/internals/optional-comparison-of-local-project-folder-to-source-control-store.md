---
title: 소스 제어 저장소를 로컬 프로젝트 폴더의 선택적 비교 | Microsoft Docs
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
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 359b5e0e2eb3b2a90e3860bdd2664641580971d2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51784106"
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>로컬 프로젝트 폴더와 소스 제어 저장소의 선택적 비교
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

원본 제어 플러그 인 API 1.2 로컬 프로젝트 폴더 및 소스 제어 간의 비교 함수를 사용 하 여 이루어집니다 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) 하 고 [SccDirDiff](../../extensibility/sccdirdiff-function.md)합니다.  
  
 내 **솔루션 탐색기**폴더를 선택 하 여 개별 파일을 대신 하는 경우를 **버전 비교** 바로 가기 메뉴를 호출 하는 새 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) 및[ SccDirDiff](../../extensibility/sccdirdiff-function.md) 소스 제어 플러그 인입니다.  
  
## <a name="new-capability-flags"></a>새 기능 플래그  
 `SCC_CAP_DIRECTORYDIFF`  
  
 `SCC_CAP_DIRECTORYCHECKOUT`  
  
## <a name="new-functions"></a>새 함수  
 [SccDirDiff](../../extensibility/sccdirdiff-function.md)  
  
 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)  
  
 합니다 `SccDirQueryInfo` 하기 전에 함수가 호출 될 `SccDirDiff` 소스 제어 작업 디렉터리 인지 확인 하려면. `SccDirDiff` 함수는 현재 로컬 디렉터리와 해당 소스 제어 폴더 간의 차이 표시 합니다. 이 명령은 디렉터리 변경 내용 목록을 표시 하려면 플러그 인 소스 제어를 요청 합니다. 소스 제어 플러그 인 차이점을 표시 하는 자체 UI를 제공 합니다.  
  
> [!NOTE]
>  이 함수는 동일한 명령 플래그를 사용 [SccDiff](../../extensibility/sccdiff-function.md)합니다. 원본 제어 플러그 인 공급자 디렉터리에 대 한 "빠른 diff" 작업을 지원 하지 않도록 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

