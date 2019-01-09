---
title: 'Iactivescriptsitetraceinfo:: Sendscripttraceinfo 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0419e4c5-eb7c-45a3-b6dc-1a5e157d95f9
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f08a5cb0e7bd297dede85190ac694185e2fd795
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091626"
---
# <a name="iactivescriptsitetraceinfosendscripttraceinfo-method"></a>IActiveScriptSiteTraceInfo::SendScriptTraceInfo 메서드
이벤트 유형, 컨텍스트 및 스크립트 문을 포함 하는 추적 정보를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SendScriptTraceInfo(     [in] SCRIPTTRACEINFO stiEventType,     [in] GUID guidContextID,     [in] DWORD dwScriptContextCookie,     [in] LONG lScriptStatementStart,     [in] LONG lScriptStatementEnd,     [in] DWORD64 dwReserved );   
```  
  
#### <a name="parameters"></a>매개 변수  
 `stiEventType`  
 이벤트 유형입니다.  
  
 `guidContextId`  
 컨텍스트의 GUID입니다.  
  
 `dwScriptContextCookie`  
 컨텍스트는 쿠키입니다.  
  
 `lScriptStatementStart`  
 스크립트 문의 시작 위치입니다.  
  
 `lScriptStatementEnd`  
 스크립트 문의 끝 위치입니다.  
  
 `dwReserved`  
 예약됨.