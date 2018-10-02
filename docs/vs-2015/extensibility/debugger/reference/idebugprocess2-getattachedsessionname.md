---
title: IDebugProcess2::GetAttachedSessionName | Microsoft Docs
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
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1ba2ad04d96f8970ca43c4f1a136d2676ed70fad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564723"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugProcess2::GetAttachedSessionName](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-getattachedsessionname)합니다.  
  
이 프로세스를 디버깅 하는 세션의 이름을 가져옵니다. IDE는 사용자에 게 특정 컴퓨터에서 특정 프로세스를 디버깅 하는이 정보를 표시할 수 있습니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않으며 해당 구현이 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrSessionName`  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

