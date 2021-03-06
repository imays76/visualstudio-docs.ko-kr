---
title: IActiveScriptSite::OnScriptError | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptError
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptError
ms.assetid: 5c9c85cc-21ad-4232-be83-a24cc7570108
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d2c9cb95615ad0b978cc7fd9943b687e5a7f3cac
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344566"
---
# <a name="iactivescriptsiteonscripterror"></a>IActiveScriptSite::OnScriptError
엔진을 스크립트를 실행 하는 동안 실행 오류가 발생 했음을 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT OnScriptError(  
    IActiveScriptError *pase  // address of error interface  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pase`  
 [in] 오류 개체의 주소 [IActiveScriptError](../../winscript/reference/iactivescripterror.md) 인터페이스입니다. 호스트는이 인터페이스를 사용 하 여 실행 오류에 대 한 정보를 가져올 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` OLE 오류 코드를 그렇지 않으면 정의 또는 오류를 올바르게 처리 하는 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)