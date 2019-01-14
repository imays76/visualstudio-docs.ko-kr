---
title: 'Idiasession:: Findinjectedsource | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a16e3827999d165f0d04b803e4d0611bf4f2538d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851998"
---
# <a name="idiasessionfindinjectedsource"></a>IDiaSession::findInjectedSource
컴파일 프로세스의 다른 구성 요소 또는 특성 공급자에 의해 기호 저장소에 배치 된 원본 목록을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findInjectedSource (   
   LPCOLESTR                 srcFile,  
   IDiaEnumInjectedSources** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 srcFile  
 [in] 검색할 소스 파일의 이름입니다.  
  
 ppResult  
 [out] 반환 된 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) 삽입 된 원본의 모든 목록을 포함 하는 개체.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)