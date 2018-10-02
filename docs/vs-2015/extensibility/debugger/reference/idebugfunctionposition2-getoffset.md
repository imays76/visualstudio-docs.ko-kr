---
title: IDebugFunctionPosition2::GetOffset | Microsoft Docs
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
- IDebugFunctionPosition2::GetOffset
helpviewer_keywords:
- IDebugFunctionPosition2::GetOffset
ms.assetid: 60943782-aec7-4be2-b222-1984ed53a543
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3cdfcaa8302d2c9d72ad0d0156a07a06f9e4bdf0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564537"
---
# <a name="idebugfunctionposition2getoffset"></a>IDebugFunctionPosition2::GetOffset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugFunctionPosition2::GetOffset](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionposition2-getoffset)합니다.  
  
소스 문서에서 함수의 위치를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetOffset(   
   TEXT_POSITION* pPosition  
);  
```  
  
```csharp  
int GetOffset(  
   TEXT_POSITION[] pPosition  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pPosition`  
 [out에서] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조는 문서에서 함수의 위치를 사용 하 여 입력 됩니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)

