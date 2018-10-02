---
title: StopTrackingAndCleanup | Microsoft Docs
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
- StopTrackingAndCleanup
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- StopTrackingAndCleanup
ms.assetid: 9f8c5994-2dfc-43c3-a5fb-89b2f8990429
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 39471ea7f88849151e9f6c0c6cc65bdd913d7af2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550157"
---
# <a name="stoptrackingandcleanup"></a>StopTrackingAndCleanup
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [StopTrackingAndCleanup](https://docs.microsoft.com/visualstudio/msbuild/stoptrackingandcleanup)합니다.  
  
  
모든 추적을 중지하고 추적 세션에 사용된 메모리를 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WINAPI StopTrackingAndCleanup(void);  
```  
  
## <a name="return-value"></a>반환 값  
 [HRESULT]를 반환 합니다 (<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) [성공]를 사용 하 여 (<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) 추적이 중지 된 경우에 비트가 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h  
  
## <a name="see-also"></a>참고 항목  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)



