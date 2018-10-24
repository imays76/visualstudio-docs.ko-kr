---
title: 'Idiasession:: Findfilebyid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7c56d66a78b52e99aecb8cb744cc3d8465d0d243
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49941414"
---
# <a name="idiasessionfindfilebyid"></a>IDiaSession::findFileById
원본 파일 식별자에서 소스 파일을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `uniqueId`  
 [in] 소스 파일 식별자를 지정합니다.  
  
 `ppResult`  
 [out] 반환을 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 소스 파일을 나타내는 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 소스 파일 식별자에는 모든 소스 파일을 고유 하 게 DIA SDK를 내부적으로 사용 되는 고유 값입니다. 이 메서드는 일반적으로 DIA SDK를 내부적으로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession:: Findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)