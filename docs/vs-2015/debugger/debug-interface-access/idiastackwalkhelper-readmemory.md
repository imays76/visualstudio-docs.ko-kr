---
title: IDiaStackWalkHelper::readMemory | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c843291aa87671d11293b72795222af9e96b03d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49904431"
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

메모리에서 실행 파일의 이미지에서 데이터 블록을 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT readMemory(   
   enum MemoryTypeEnum type,  
   ULONGLONG           va,  
   DWORD               cbData,  
   DWORD*              pcbData,  
   BYTE*               pbData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 [in] 값을 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md) 읽어 올 메모리를의 형식을 지정 하는 합니다.  
  
 Va  
 [in] 읽기를 시작 하는 이미지에서 가상 주소입니다.  
  
 `cbData`  
 [in] 바이트 데이터 버퍼의 크기입니다.  
  
 `pcbData`  
 [out] 실제로 읽은 바이트 수를 반환 합니다. 하는 경우 `pbData` 는 `NULL`를 사용할 수 있는 데이터의 바이트의 총 수입니다.  
  
 `pbData`  
 [out에서] 읽을 메모리를 사용 하 여 입력 되는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md)



