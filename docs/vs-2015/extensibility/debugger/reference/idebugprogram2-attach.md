---
title: IDebugProgram2::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4c64b4839d2f16adfcf40b082d54f60a95d7a468
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49881642"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

프로그램에 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Attach(   
   IDebugEventCallback2* pCallback  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버그 이벤트 알림에 사용할 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 다음 표에서 몇 가지 가능한 오류 코드를 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|지정된 된 프로그램 디버거가 이미 연결 되어 있습니다.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|연결 절차 동안 보안 위반이 발생 했습니다.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|데스크톱 프로그램 디버거를 연결할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 디버그 엔진 (DE) 프로그램에 연결 하려면이 메서드를 호출 하지 않습니다. 프로그램의 주소 공간에서 실행 되는 DE 합니다 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드가 호출 됩니다. (SDM) 세션 디버그 관리자에서 DE 실행 주소 공간을 하는 경우는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드가 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)

