---
title: 'Idiaenumtables:: Get__newenum | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::get__NewEnum method
ms.assetid: 7b1159c7-a5f0-4baa-861a-dc11437d8b93
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ac55dca49d954663b8db71903348d2f538ebd39d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49917039"
---
# <a name="idiaenumtablesgetnewenum"></a>IDiaEnumTables::get__NewEnum
검색 된 <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> 이 열거자의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 반환 된 `IUnknown` 나타내는 인터페이스입니다는 <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> 이 열거자의 버전.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)