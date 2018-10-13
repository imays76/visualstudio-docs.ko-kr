---
title: IEEDataStorage::GetData | Microsoft Docs
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
- IEEDataStorage::GetData
helpviewer_keywords:
- IEEDataStorage::GetData
ms.assetid: 4d384039-73d4-40b4-ace6-a2474c546397
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: be6b411ae5881dbcfcfc51de98d5b67cd57e8048
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49188129"
---
# <a name="ieedatastoragegetdata"></a>IEEDataStorage::GetData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

개체에서 지정 된 바이트 수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetData(  
   ULONG  dataSize,  
   ULONG* sizeGotten,  
   BYTE*  data  
);  
```  
  
```csharp  
int GetData(  
   uint     dataSize,  
   out uint sizeGotten,  
   byte[]   data  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dataSize`  
 [in] 검색할 바이트 수 (의 `data` 배열 최소 바이트이 수가이 보유 해야 합니다).  
  
 `sizeGotten`  
 [out] 실제로 검색 하는 바이트 수를 반환 합니다.  
  
 `data`  
 [out에서] 요청한 데이터를로 채워질 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 권장 되는이 방법 사용 검색 프로세스에서 바이트를 건너뛸 수 없기 때문 로컬 배열로 모든 데이터 바이트를 검색 하는 것입니다. 이 예에서 매개 변수 `dataSize` 값에서 반환 해야 합니다 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)

