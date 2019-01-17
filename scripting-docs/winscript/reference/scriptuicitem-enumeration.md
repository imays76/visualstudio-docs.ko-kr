---
title: SCRIPTUICITEM 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fbf01f1b-5d7f-4d92-8d10-3da65e352d93
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cf880ed8b0295e841026e884f6cec71a9f52d4ae
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347491"
---
# <a name="scriptuicitem-enumeration"></a>SCRIPTUICITEM 열거형
UI 항목의 유형을 나타냅니다. 에 사용 된 [iactivescriptsiteuicontrol:: Getuibehavior 메서드](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
typedef enum tagSCRIPTUICITEM {     SCRIPTUICITEM_INPUTBOX = 1,     SCRIPTUICITEM_MSGBOX = 2,     } SCRIPTUICITEM;   
```  
  
## <a name="enumeration-values"></a>열거형 값  
  
|||  
|-|-|  
|SCRIPTUICITEM_INPUTBOX|입력된 컨트롤입니다.|  
|SCRIPTUICITEM_MSGBOX|메시지 상자입니다.|