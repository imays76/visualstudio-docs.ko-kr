---
title: IDebugField::GetInfo | Microsoft Docs
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
- IDebugField::GetInfo
helpviewer_keywords:
- IDebugField::GetInfo method
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eb4709321c60f812f1f5211cc9f2c065d3f0a236
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51741617"
---
# <a name="idebugfieldgetinfo"></a>IDebugField::GetInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 필드를 표시할 수 있는 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetInfo(   
   FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO* pFieldInfo  
);  
```  
  
```csharp  
int GetInfo(  
   enum_FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO[] pFieldInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFields`  
 [in] 조합을 [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) 표시할 정보를 선택 하는 상수입니다. 필드 기호를 나타내는 경우 이것이 일반적으로 기호 이름과 형식입니다.  
  
 `pFieldInfo`  
 [out] 제공 된 정보를 반환 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)

