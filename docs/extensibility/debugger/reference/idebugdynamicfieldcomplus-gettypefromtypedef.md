---
title: IDebugDynamicFieldCOMPlus::GetTypeFromTypeDef | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetTypeFromTypeDef
- IDebugDynamicFieldCOMPlus::GetTypeFromTypeDef
ms.assetid: 7f6cd3d3-f4da-4893-be91-8dd104be8010
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0238da9c435fcfc02aacf00e4e54459d0fc59c10
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49853234"
---
# <a name="idebugdynamicfieldcomplusgettypefromtypedef"></a>IDebugDynamicFieldCOMPlus::GetTypeFromTypeDef
해당 토큰을 지정 하는 형식을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeFromTypeDef(  
   ULONG32       ulAppDomainID,  
   GUID          guidModule,  
   _mdToken      tokClass,  
   IDebugField** ppType  
);  
```  
  
```csharp  
int GetTypeFromTypeDef(  
   uint            ulAppDomainID,  
   Guid            guidModule,  
   int             tokClass,  
   out IDebugField ppType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ulAppDomainID`  
 [in] 응용 프로그램 도메인의 식별자입니다.  
  
 `guidModule`  
 [in] 모듈의 고유 식별자입니다.  
  
 `tokClass`  
 [in] 토큰 형식을 나타내는입니다.  
  
 `ppType`  
 [out] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 형식을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)