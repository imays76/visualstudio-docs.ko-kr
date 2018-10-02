---
title: IDebugDocumentText2::GetSize | Microsoft Docs
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
- IDebugDocumentText2::GetSize
helpviewer_keywords:
- IDebugDocumentText2::GetSize
ms.assetid: bf515a8f-dcee-4004-8f81-543d547ceaae
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d7b3c5d5c401580007efca659d749548d25e210
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47557446"
---
# <a name="idebugdocumenttext2getsize"></a>IDebugDocumentText2::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugDocumentText2::GetSize](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdocumenttext2-getsize)합니다.  
  
문서의이 위치에서 텍스트의 크기를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetSize(   
   ULONG* pcNumLines,  
   ULONG* pcNumChars  
);  
```  
  
```csharp  
int GetSize(   
   ref uint pcNumLines,  
   ref uint pcNumChars  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcNumLines`  
 [out] 텍스트 줄의 수를 반환합니다.  
  
 `pcNumChars`  
 [out] 텍스트의 문자 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 [C + + 전용] 특정 값을 원하지 않는 경우 매개 변수에 대해 NULL을 전달 합니다.  
  
 [C#만 해당] 매개 변수를 모두 지정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)

