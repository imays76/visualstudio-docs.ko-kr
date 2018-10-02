---
title: IDebugMethodField::GetGlobalContainer | Microsoft Docs
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
- IDebugMethodField::GetGlobalContainer
helpviewer_keywords:
- IDebugMethodField::GetGlobalContainer method
ms.assetid: 041ac5aa-0b80-4310-b9ae-b88f8e7e0e5f
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aec4171c4e1203c8637e0d03bb7c031442813bf8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551573"
---
# <a name="idebugmethodfieldgetglobalcontainer"></a>IDebugMethodField::GetGlobalContainer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugMethodField::GetGlobalContainer](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmethodfield-getglobalcontainer)합니다.  
  
메서드의 전역 컨테이너를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetGlobalContainer(  
   IDebugClassField** ppClass  
);  
```  
  
```csharp  
int GetGlobalContainer(  
   out IDebugClassField ppClass  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppClass`  
 [out] 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 이 메서드가 정의 되어 있는 모듈을 나타내는입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 개체는 전체 모듈 나타내며 인위적인 개체, 즉, 모듈 자체는 실제 클래스 없지만로 나타낼 수 있습니다는 `IDebugClassField` 허용 하는 다양 한 개체 열거 하 고 발견 된 모듈의 요소입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)

