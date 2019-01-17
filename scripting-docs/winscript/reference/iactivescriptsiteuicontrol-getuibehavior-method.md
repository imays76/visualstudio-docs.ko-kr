---
title: 'Iactivescriptsiteuicontrol:: Getuibehavior 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9a944335-856a-4c6b-b2bc-8872542941b7
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b52c94e9c8b14218362000df401fba24568ea426
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344800"
---
# <a name="iactivescriptsiteuicontrolgetuibehavior-method"></a>IActiveScriptSiteUIControl::GetUIBehavior 메서드
가져옵니다를 [SCRIPTUICHANDLING 열거형](../../winscript/reference/scriptuichandling-enumeration.md) 나타내는 UI 컨트롤을 처리 해야 하는 방식입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetUIBehavior(     [in] SCRIPTUICITEM UicItem,     [out] SCRIPTUICHANDLING * pUicHandling );   
```  
  
#### <a name="parameters"></a>매개 변수  
 `UicItem`  
 컨트롤의 형식입니다.  
  
 `pUicHandling`  
 컨트롤을 처리 해야 하는 방법입니다.