---
title: CPPClean 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.task.cppclean
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CPPClean task
- CPPClean task (MSBuild (Visual C++))
ms.assetid: b62a482e-8fb5-4999-b50b-6605a078e291
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a96571cbc4de4281daddd42f4b1d53b60b300e53
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49826949"
---
# <a name="cppclean-task"></a>CPPClean 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]


Visual C++ 프로젝트가 빌드될 때 MSBuild가 만드는 임시 파일을 삭제합니다. 빌드 파일을 삭제하는 프로세스는 *정리*라고 합니다.  

## <a name="parameters"></a>매개 변수  
 다음 표에서는 **CPPClean** 작업의 매개 변수에 대해 설명합니다.  


|            매개 변수            |                                                                                                설명                                                                                                 |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        **DeletedFiles**         |                               선택적 `ITaskItem[]` 출력 매개 변수입니다.<br /><br /> 작업에서 사용하고 내보낼 수 있는 MSBuild 출력 파일 항목의 배열을 정의합니다.                                |
|          **DoDelete**           |                                                            선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 임시 빌드 파일을 정리합니다.                                                             |
| **FilePatternsToDeleteOnClean** |                                            필수 `String` 매개 변수입니다.<br /><br /> 정리할 파일의 확장명을 세미콜론으로 구분된 목록으로 지정합니다.                                             |
|   **FilesExcludedFromClean**    |                                                    선택적 `String` 매개 변수입니다.<br /><br /> 정리하지 않을 파일을 세미콜론으로 구분된 목록으로 지정합니다.                                                    |
|       **FoldersToClean**        | 필수 `String` 매개 변수입니다.<br /><br /> 정리할 디렉터리를 세미콜론으로 구분된 목록으로 지정합니다. 전체 또는 상대 경로 지정 하 고 경로 와일드 카드 기호를 포함할 수 있습니다 (**\\**\*). |

## <a name="remarks"></a>설명  

## <a name="see-also"></a>참고 항목  
 [작업 참조](../msbuild/msbuild-task-reference.md)



