---
title: IDebugProcess2::Detach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: de18df907c8a30235fcfc3391fe6879afdcaa1f9
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49854301"
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