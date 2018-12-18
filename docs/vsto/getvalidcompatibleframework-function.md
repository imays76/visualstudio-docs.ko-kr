---
title: GetValidCompatibleFramework 함수
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8cc16544df224e09724cae8a1f09f72039cb61e5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49894497"
---
# <a name="getvalidcompatibleframework-function"></a>GetValidCompatibleFramework 함수
  이 API는 Office 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.  

## <a name="syntax"></a>구문  

```csharp 
HRESULT WINAPI GetValidCompatibleFramework(  
    LPCWSTR lpwszCompatibleFrameworksXML,  
    BSTR* pbstrValidFrameworkTag  
);  
```  

### <a name="parameters"></a>매개 변수  

|매개 변수|설명|  
|---------------|-----------------|  
|*lpwszCompatibleFrameworksXML*|사용 하지 마세요.|  
|*pbstrValidFrameworkTag*|사용 하지 마세요.|  

## <a name="return-value"></a>반환 값  
 함수가 성공 하는 경우 반환 **S_OK**합니다. 함수가 실패할 경우 오류 코드를 반환 합니다.  

