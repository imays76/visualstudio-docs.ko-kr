---
title: 디렉터리 상태 코드 열거자 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a8d6a541415e42e8d35dc4f3ab814c89cf939beb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53927612"
---
# <a name="directory-status-code-enumerator"></a>디렉터리 상태 코드 열거자
`SccDirStatus` 소스 제어 시스템에서 디렉터리의 상태를 지정 하는 명명 된 상수 값을 포함 하는 열거자입니다. 이 열거형은에서 사용 된 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)합니다. 이 원본 제어 플러그 인 API 버전 1.2에에서 도입 되었습니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>멤버  
 SCC_DIRSTATUS_INVALID  
 상태를 가져올 수 없습니다. 이에 의존 하지 않습니다.  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 디렉터리를 소스 제어에 없습니다.  
  
 SCC_DIRSTATUS_CONTROLLED  
 소스 제어 디렉터리가 있습니다.  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 이 디렉터리에 해당 하는 프로젝트가 비어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [원본 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)