---
title: '방법: 명령줄에서 보고서 필터링 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb8df34291d99d093ccf0d053d5dd1fbe2955232
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51789787"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>방법: 명령줄에서 보고서 필터링
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**VSPerfReport** 명령에 대한 옵션을 사용하여 프로파일링 데이터 파일의 특정 시간 세그먼트에 대한 보고서를 필터링하거나 데이터를 하나 이상의 프로세스 또는 스레드로 제한할 수 있습니다. 이 명령에 대한 자세한 내용은 [VSPerfReport](../profiling/vsperfreport.md)를 참조하세요.  
  
|옵션|설명|  
|-------------|-----------------|  
|**StartTime:**[*Value*]|value 이후에 수집된 데이터만 표시합니다(밀리초).|  
|**EndTime:**[*Value*]|value 이전에 수집된 데이터만 표시합니다(밀리초).|  
|**FilterFile:** `VSPFFile`|**Visual Studio 성능 보고서** 창에서 생성된 필터 파일의 위치를 지정합니다.|  
|**MsFilter:**[*StartTime,Duration*]|`StartTime`부터 `Duration` 길이(밀리초)까지의 데이터만 표시합니다.|  
|**Process:**[*Pid*]|지정한 프로세스의 데이터만 표시합니다.|  
|**Thread:**[*ThreadID*]|지정한 스레드의 데이터만 표시합니다.|  
|**Thread:**[*ThreadID,ProcessID*]|지정한 프로세스와 관련된 특정 스레드의 데이터만 표시합니다.|



