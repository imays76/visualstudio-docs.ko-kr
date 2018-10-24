---
title: BP_LOCATION_CODE_STRING | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_STRING
helpviewer_keywords:
- BP_LOCATION_CODE_STRING structure
ms.assetid: a4cd71c6-5052-45fe-907b-ebc6ca1df2e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 31b7baad0350ef0524aee81e61f9019b8e91a9de
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49857148"
---
# <a name="bplocationcodestring"></a>BP_LOCATION_CODE_STRING
통합된 개발 환경 (IDE)에서 사용자가 입력할 수 있는 문자열을 기반으로 코드 중단점을 설정 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_LOCATION_CODE_STRING {   
   BSTR bstrContext;  
   BSTR bstrCodeExpr;  
} BP_LOCATION_CODE_STRING;  
```  
  
## <a name="members"></a>멤버  
 `bstrContext`  
 코드 내에서 중단점, 호출 스택에 표시 된 메서드 또는 함수 이름 일반적으로의 컨텍스트.  
  
 `bstrCodeExpr`  
 사용자가에 코드 중단점을 설명 하는 문자열입니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 멤버인 합니다 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 공용 구조체의 일부로 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)