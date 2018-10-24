---
title: IDebugProgram2::Detach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Detach
helpviewer_keywords:
- IDebugProgram2::Detach
ms.assetid: 5e8d88b0-a8d4-4746-88c0-ad332ee73f33
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ff18f393c609faed6f5aeadbec9903f2d5a5dab5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49832538"
---
# <a name="idebugprogram2detach"></a>IDebugProgram2::Detach
프로그램에서 디버그 엔진을 분리합니다.  
  
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
 분리 된 프로그램 실행을 계속 이지만 더 이상 디버그 세션에 포함 합니다. 프로그램 디버그 이벤트가 더 이상 디버그 엔진 분리 되 면 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)