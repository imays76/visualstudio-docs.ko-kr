---
title: IDebugExtendedField::IsClosedType | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a566f5dc7d498a9b07d132abe35b279cbc83155d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543815"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugExtendedField::IsClosedType](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugextendedfield-isclosedtype)합니다.  
  
필드 닫힌된 형식을 나타내는지 여부를 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>반환 값  
 필드에 닫힌된 형식이 면 반환 `S_OK`이 고, 그렇지 않으면 반환 `S_FALSE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)

