---
title: StackFrameTypeEnum | Microsoft Docs
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
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 081be0d7b9369462bae703b571629897bd5df94c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543726"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [StackFrameTypeEnum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/stackframetypeenum)합니다.  
  
스택 프레임 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum StackFrameTypeEnum {  
   FrameTypeFPO,  
   FrameTypeTrap,  
   FrameTypeTSS,  
   FrameTypeStandard,  
   FrameTypeFrameData,  
   FrameTypeUnknown = -1  
};  
```  
  
## <a name="elements"></a>요소  
 `FrameTypeFPO`  
 프레임 포인터 생략 합니다. FPO 정보를 사용할 수 있습니다.  
  
 `FrameTypeTrap`  
 커널 트랩 프레임입니다.  
  
 `FrameTypeTSS`  
 커널 트랩 프레임입니다.  
  
 `FrameTypeStandard`  
 표준 EBP 스택 프레임입니다.  
  
 `FrameTypeFrameData`  
 프레임 포인터 생략 합니다. 프레임 데이터 정보를 사용할 수 있습니다.  
  
 `FrameTypeUnknown`  
 모든 디버그 정보가 없는 프레임입니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값에는 호출에서 반환 되는 [idiastackframe:: Get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)



