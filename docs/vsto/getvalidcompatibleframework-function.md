---
title: GetValidCompatibleFramework 함수
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 30a116993535e3b99b4e91edf07752c00a020859
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53835489"
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
