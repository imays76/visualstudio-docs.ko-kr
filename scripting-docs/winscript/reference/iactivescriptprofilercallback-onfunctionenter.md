---
title: IActiveScriptProfilerCallback::OnFunctionEnter | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.OnFunctionEnter
apilocation:
- scrobj.dll
ms.assetid: 12dab2b4-df4e-444d-99cb-25e1c278e6e8
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 887810d12a20045c95b0f837db1592b9b7bf301e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095383"
---
# <a name="iactivescriptprofilercallbackonfunctionenter"></a>IActiveScriptProfilerCallback::OnFunctionEnter
문서 개체 모델 (DOM)를 호출 하지 않은 함수 호출을 실행 하는 스크립팅 엔진 프로파일러 개체를 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT OnFunctionEnter(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scriptId`  
 [in] 함수가 포함 된 스크립트의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `functionId`  
 [in] 함수의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진 호출 DOM 호출용 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md) 대신 `IActiveScriptProfilerCallback::OnFunctionEnter`합니다. Dom의 고유한 메서드 및 속성 수가 많기 때문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)   
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)