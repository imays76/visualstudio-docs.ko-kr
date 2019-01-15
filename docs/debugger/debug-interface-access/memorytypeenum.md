---
title: MemoryTypeEnum | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MemoryTypeEnum enumeration
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a83a37a3aa454885d714be667ca7678ae543ff09
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875918"
---
# <a name="memorytypeenum"></a>MemoryTypeEnum
메모리 액세스의 형식을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `MemTypeCode`  
 액세스는 메모리 에서만 코드입니다.  
  
 `MemTypeData`  
 데이터 또는 스택 메모리 액세스 합니다.  
  
 `MemTypeStack`  
 만 스택 메모리를 액세스 합니다.  
  
 `MemTypeAny`  
 모든 종류의 메모리에 액세스합니다.  
  
## <a name="remarks"></a>주의  
 이 열거형의 값에 전달 되는 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md) 다양 한 유형의 메모리에 대 한 액세스를 제한 하는 방법이 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)