---
title: METADATA_ADDRESS_LOCAL | Microsoft Docs
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
- METADATA_ADDRESS_LOCAL
helpviewer_keywords:
- METADATA_ADDRESS_LOCAL structure
ms.assetid: 635f6bc5-c486-4e0e-83db-36f15e543843
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d59951fa73b4f5f10ab26abaad65fc2beab54837
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556671"
---
# <a name="metadataaddresslocal"></a>METADATA_ADDRESS_LOCAL
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [METADATA_ADDRESS_LOCAL](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/metadata-address-local)합니다.  
  
이 구조 (일반적으로 함수 또는 메서드) 범위 내에서 로컬 변수의 주소를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_LOCAL {  
   _mdToken  tokMethod;  
   IUnknown* pLocal;  
   DWORD     dwIndex;  
} METADATA_ADDRESS_LOCAL;  
```  
  
```csharp  
public struct METADATA_ADDRESS_LOCAL {  
   public int    tokMethod;  
   public object pLocal;  
   public uint   dwIndex;  
}  
```  
  
## <a name="terms"></a>용어  
 tokMethod  
 메서드 또는 함수의 ID 지역 변수는 부분입니다.  
  
 [C + +] `_mdToken` 되는 `typedef` 32 비트 `int`합니다.  
  
 pLocal  
 이 구조를 나타내는 해당 주소가 토큰입니다.  
  
 dwIndex  
 메서드 또는 함수 또는 다른 값 (언어별)이 지역 변수의 인덱스를 수 있습니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 공용 구조체의 일부인를 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 경우 구조체를 `dwKind` 필드를 `DEBUG_ADDRESS_UNION` 구조로 설정 되어 `ADDRESS_KIND_LOCAL` (의 값을 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형)입니다.  
  
 `Warning:` [C + + 전용]  경우 `pLocal` is not null을 호출 해야 합니다 `Release` 토큰 포인터 (`addr` 에 있는 필드를 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 구조):  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)

