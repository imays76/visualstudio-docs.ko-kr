---
title: IActiveScriptSiteWindow | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteWindow interface
ms.assetid: 96d5c493-2c0b-47e2-848b-4a8dacdcd65c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a160b17f4a46237ab78b378664a046fe8a0e7d4
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345723"
---
# <a name="iactivescriptsitewindow"></a>IActiveScriptSiteWindow
이 인터페이스와 같은 개체에는 사용자 인터페이스를 지 원하는 호스트에 의해 구현 됩니다 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 합니다. 서버와 같은 사용자 인터페이스를 지원 하지 않는 호스트를 구현 하지 않습니다는 `IActiveScriptSiteWindow` 인터페이스입니다. 이 인터페이스를 호출 하 여 액세스 하는 스크립팅 엔진 `QueryInterface` 에서 `IActiveScriptSite`합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptSiteWindow::GetWindow](../../winscript/reference/iactivescriptsitewindow-getwindow.md)|소유자는 스크립팅 엔진을 표시 해야 하는 팝업 창 사용할 수 있는 창 핸들을 검색 합니다.|  
|[IActiveScriptSiteWindow::EnableModeless](../../winscript/reference/iactivescriptsitewindow-enablemodeless.md)|호스트를 사용 하도록 설정 하거나 주 창 뿐만 아니라 모든 모덜리스 대화 상자를 사용 하지 않도록 하면 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)