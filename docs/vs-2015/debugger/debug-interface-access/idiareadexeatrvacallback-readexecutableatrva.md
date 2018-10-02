---
title: 'Idiareadexeatrvacallback:: Readexecutableatrva | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c0c6f5cfc7c125eb2a90b744ce038c344b192ff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47544045"
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiareadexeatrvacallback:: Readexecutableatrva](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva)합니다.  
  
지정된 된 상대 가상 주소에 (RVA) 실행 파일에서 시작 하는 바이트의 지정 된 수를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT ReadExecutableAtRVA (   
   DWORD  relativeVirtualAddress,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `relativeVirtualAddress`  
 [in] 읽기를 시작할 실행 파일에 RVA입니다.  
  
 `cbData`  
 [in] 읽을 바이트 수입니다.  
  
 `pcbData`  
 [out] 읽은 바이트 수를 반환 합니다.  
  
 `data[]`  
 [out에서] 파일에서 읽은 바이트를 사용 하 여 입력은 배열입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 DIA 지원 코드 상대 가상 주소를 사용 하 여 실행 파일에서 데이터 바이트를 로드 하 여 호출 됩니다. 이 메서드를 지 원하는 호출을 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)



