---
title: IDiaStackWalker::getEnumFrames | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames method
ms.assetid: f9f09729-4c34-441c-989c-e0b7339ee32c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f4c7d8d30dee1d9c0a058177ad54aab864cee28d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49836164"
---
# <a name="idiastackwalkergetenumframes"></a>IDiaStackWalker::getEnumFrames
X86에 대 한 스택 프레임 열거자를 검색 플랫폼입니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT getEnumFrames(   
   IDiaStackWalkHelper*   pHelper,  
   IDiaEnumStackFrames**  ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pHelper`  
 [in] 도우미 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) 개체입니다.  
  
 `ppEnum`  
 [out] 반환 된 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md) 개체의 목록을 포함 하는 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 다른 플랫폼에서 스택 프레임 목록을 가져오려면를 호출 합니다 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)