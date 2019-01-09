---
title: IScriptNode::GetChild | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetChild
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetChild
ms.assetid: 8cb3f8b0-958b-40bb-a91a-49a788661861
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55cd6cf5233e850e4109128e322d3fc5bd0b1355
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086595"
---
# <a name="iscriptnodegetchild"></a>IScriptNode::GetChild
노드에 지정된 된 인덱스에 있는 자식을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetChild(  
   ULONG              isn,  
   IScriptNode        **ppsn  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `isn`  
 [in] 부모에서 자식 항목의 인덱스입니다.  
  
 `ppsn`  
 [out] 에 대 한 포인터를 받는 변수의 주소는 `IScriptNode` 자식 인스턴스는 인터페이스입니다.  
  
 에 대 한 `IScriptNode` 웹 페이지를 나타내는 개체를이 매개 변수는 스크립트 블록을 포함 하는 개체를 반환 합니다.  
  
 에 대 한 `IScriptEntry` 스크립트 블록을 지정 하는 개체를이 매개 변수는 함수를 지정 하는 개체를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 에 대 한 `IScriptEntry` 함수를 지정 하는 개체 및 `IScriptScriptlet` 개체에 자식 항목이 있기 때문에이 메서드는 실패 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)