---
title: IDiaStackWalkHelper::put_registerValue | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::put_registerValue method
ms.assetid: 8f02ce54-ef59-455f-8aa6-dc26761c7aff
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4936d33150f38ed84a03b1d3a1b661bdb402bb64
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541845"
---
# <a name="idiastackwalkhelperputregistervalue"></a>IDiaStackWalkHelper::put_registerValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDiaStackWalkHelper::put_registerValue](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-put-registervalue)합니다.  
  
레지스터의 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT put_registerValue (   
   DWORD     index,  
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 [in] 값을 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 쓸 레지스터를 지정 하는 열거형입니다.  
  
 `NewVal`  
 [in] 새 값을 등록합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 값의 크기에도 불구 하 고 구현만 무엇입니까 레지스터 일반적으로 보유 저장 해야 합니다. 예를 들어, 8 비트 레지스터를 가장 낮은 8-비트만 지정된 된 값의 저장 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)



