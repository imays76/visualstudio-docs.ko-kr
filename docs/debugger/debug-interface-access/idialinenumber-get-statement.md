---
title: 'Idialinenumber:: Get_statement | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_statement method
ms.assetid: 22b8ee29-79ef-427f-bd05-00d255ab836b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c6b16d142f5bdc83b9a16e3299c15a0c845cf2c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53949325"
---
# <a name="idialinenumbergetstatement"></a>IDiaLineNumber::get_statement
이 줄 정보 프로그램 소스에 식 대신 문을 시작 부분을 설명 하는지 나타내는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_statement (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 `TRUE` 이 줄 정보 프로그램 원본에서 문의 시작 부분에 대해 설명 하는 경우.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`를 반환합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>주의  
 문을 여러 줄으로 나누어 입력할 수 있습니다. 이 메서드는 연결 된 줄 번호를 이러한 여러 줄 문의 시작을 표시 하는 경우를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)