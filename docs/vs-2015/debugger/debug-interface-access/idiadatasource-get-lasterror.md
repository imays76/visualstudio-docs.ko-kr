---
title: 'Idiadatasource:: Get_lasterror | Microsoft Docs'
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
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: abe45a8d86361c3bb3af458ca1352fb269dbd82d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554868"
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiadatasource:: Get_lasterror](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiadatasource-get-lasterror)합니다.  
  
마지막 로드 오류에 대 한 파일 이름을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pRetVal  
 [out] 마지막 로드 오류와 관련 된.pdb 파일 이름을 포함 하는 문자열을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 로드 작업으로 인 한 마지막 오류 코드를 반환 합니다. 반환 `E_INVALIDARG` 경우는 `pRetVal` 매개 변수는 `NULL`합니다.  
  
## <a name="example"></a>예제  
  
```cpp#  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)



