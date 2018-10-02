---
title: IDebugBinder3::GetExceptionObjectAndType | Microsoft Docs
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
- IDebugBinder3::GetExceptionObjectAndType
helpviewer_keywords:
- IDebugBinder3::GetExceptionObjectAndType method
ms.assetid: 2a313fe1-4ee1-4f01-af86-382d6c661a8f
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ae8635e1b0888b40d668040959cade3c900f04d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543598"
---
# <a name="idebugbinder3getexceptionobjectandtype"></a>IDebugBinder3::GetExceptionObjectAndType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugBinder3::GetExceptionObjectAndType](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder3-getexceptionobjectandtype)합니다.  
  
있는 경우이 메서드는 개체와 연결 된 예외를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetExceptionObjectAndType(  
   IDebugObject** ppException,  
   IDebugField**  ppField  
);  
```  
  
```csharp  
int GetExceptionObjectAndType(  
   out IDebugObject ppException,  
   out IDebugField  ppField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppException`  
 [out] 예외를 나타내는 개체를 반환 합니다.  
  
 `ppField`  
 [out] (Null 값일 수 있습니다) 예외를 일으킬 수 있는 특정 필드를 나타내는 개체를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  예외가 있는지 여부를 확인 하려면 반환 하는 값을 확인 `ppException`: 예외가 없으면이 개체와 연결 된 경우 null 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)

