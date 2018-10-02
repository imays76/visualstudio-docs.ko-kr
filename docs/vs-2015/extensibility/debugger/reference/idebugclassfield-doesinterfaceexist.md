---
title: IDebugClassField::DoesInterfaceExist | Microsoft Docs
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
- IDebugClassField::DoesInterfaceExist
helpviewer_keywords:
- IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: af7c4db5d7515d9de49ab8ffda40acfda521a5df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551756"
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugClassField::DoesInterfaceExist](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugclassfield-doesinterfaceexist)합니다.  
  
특정 인터페이스를 클래스에 정의 된 경우를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszInterfaceName`  
 [in] 검색할 인터페이스 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환, S_FALSE를 반환 합니다 인터페이스가 없는 경우 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 적용 모든 인터페이스의 열거형을 가져옵니다 및 일치 하는 인터페이스에 대 한 목록을 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)

