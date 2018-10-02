---
title: '방법: 편집기에서 포커스를 잃을 때 이벤트를 발생 시키는 | Microsoft Docs'
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
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2462e41470b72c63f5c96a69d2776af2a640c372
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551031"
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>방법: 편집기에서 포커스를 잃을 때 이벤트 발생
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 실행 이벤트 경우의 편집기를 잃을 포커스](https://docs.microsoft.com/visualstudio/extensibility/how-to-fire-events-when-the-editor-loses-focus)합니다.  
  
경우에 따라 편집기 창 프레임에 포커스를 잃을 때 알아야 합니다. 예를 들어, 편집기에서 포커스를 잃을 후 코드 창에서 코드를 추출 해야 합니다. 다음 절차는 포커스를 잃는 편집기에 대 한 알림을 수신 하는 단계를 제공 합니다.  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>포커스를 잃는 편집기에 대 한 응답에서 이벤트를 발생 시키는  
  
1.  확보 하 여 선택 이벤트를 모니터링 합니다.는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> 에서 개체 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>합니다.  
  
2.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> 제공 하면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> 개체입니다.  
  
3.  호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>를 검색할 `elementid==SEID_WindowFrame`합니다.  
  
4.  테스트는 `varValueNew` 두 가지에 대 한 매개 변수:  
  
    1.  찾고자 하는 창 프레임입니다.  
  
    2.  프로그램의 선택 영역 창 프레임을 손실는 점입니다.

