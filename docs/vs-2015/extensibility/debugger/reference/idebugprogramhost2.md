---
title: IDebugProgramHost2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramHost2
helpviewer_keywords:
- IDebugProgramHost2 interface
ms.assetid: 2c37b3aa-97a9-4665-8709-edd917f18cb1
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bd8e0b54765f20dce21eae135b0942547f967836
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553836"
---
# <a name="idebugprogramhost2"></a>IDebugProgramHost2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugProgramHost2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramhost2)합니다.  
  
이 인터페이스는 프로그램에 대 한 호스트 (process) 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramHost2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진으로 동일한 개체에서이 인터페이스를 구현 합니다 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 호스팅 프로세스에 대 한 정보를 제공 하는 인터페이스입니다. 이 선택적 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 호출 [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) 에 `IDebugProgram2` 인터페이스가이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProgramHost2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetHostName](../../../extensibility/debugger/reference/idebugprogramhost2-gethostname.md)|제목, 이름, 또는이 프로그램의 호스팅 프로세스의 파일 이름을 가져옵니다.|  
|[GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)|이 프로그램의 호스팅 프로세스의 프로세스 식별자를 가져옵니다.|  
|[GetHostMachineName](../../../extensibility/debugger/reference/idebugprogramhost2-gethostmachinename.md)|이 프로그램의 호스팅 프로세스가 실행 중인 컴퓨터의 이름을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [Core 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

