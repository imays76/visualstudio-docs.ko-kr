---
title: IDebugProcess2::Detach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::Detach
helpviewer_keywords:
- IDebugProcess2::Detach
ms.assetid: ee2b9084-2db1-4e49-a1d9-387284b7c3f8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 747430b837cf682e35f5973ea35d36e72484fb3a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53988069"
---
# <a name="idebugprocess2detach"></a>IDebugProcess2::Detach
모든 프로세스에서 프로그램을 분리 하 여이 프로세스에서 디버거를 분리 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Detach(   
   void   
);  
```  
  
```csharp  
int Detach();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 모든 프로그램 및 프로세스를 계속 실행 되지만 더 이상 디버그 세션의 일부입니다. 분리 한 후 작업이이 프로세스 (및 해당 프로그램)에 대 한 이벤트를 전송 하는 완전 하 고 더 이상 디버그 중입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)