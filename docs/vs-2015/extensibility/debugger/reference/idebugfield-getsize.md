---
title: IDebugField::GetSize | Microsoft Docs
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
- IDebugField::GetSize
helpviewer_keywords:
- IDebugField::GetSize method
ms.assetid: 73329924-3751-4f44-af54-5986b7943374
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6cfafbd4572aeb3b71992883afeafa8feffbcc69
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554463"
---
# <a name="idebugfieldgetsize"></a>IDebugField::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugField::GetSize](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfield-getsize)합니다.  
  
이 메서드는 바이트에 있는 필드의 크기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetSize(   
   DWORD* pdwSize  
);  
```  
  
```csharp  
int GetSize(  
   out uint pdwSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwSize`  
 [out] 크기를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 모든 필드 형식이 있고 모든 형식 크기입니다. 예를 들어 바이트 형식의 필드에 1 바이트의 크기.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
