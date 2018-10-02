---
title: ResumeTracking | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- ResumeTracking
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47d565bde6ef6211589e9293996c7a651ffdd8bd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551630"
---
# <a name="resumetracking"></a>ResumeTracking
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [ResumeTracking](https://docs.microsoft.com/visualstudio/msbuild/resumetracking)합니다.  
  
  
현재 컨텍스트에서 추적을 다시 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>반환 값  
 [HRESULT] (<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) [성공]를 사용 하 여 (<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) 추적이 다시 시작 된 경우에 비트가 설정 합니다. [E_FAIL] (<!-- TODO: review code entity reference <xref:assetId:///E_FAIL?qualifyHint=False&amp;autoUpgrade=True>  -->) 추적 컨텍스트를 사용할 수 없어서 재개할 수 없습니다 경우 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h  
  
## <a name="see-also"></a>참고 항목  
 [SuspendTracking](../msbuild/suspendtracking.md)



