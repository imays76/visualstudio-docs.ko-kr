---
title: 'Idiastackwalkframe:: Readmemory | Microsoft Docs'
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
- IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2fd2fe46b9be7a3181945c9fd3e58e0b087472d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942129"
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이미지에서 메모리를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT readMemory (   
   MemoryTypeEnum type,  
   ULONGLONG va,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 [in] 중 하나는 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md) 액세스 하는 메모리의 종류를 지정 하는 열거형 값입니다.  
  
 `va`  
 [in] 읽기를 시작할 이미지의 가상 주소 위치입니다.  
  
 `cbData`  
 [in] 바이트의 데이터 버퍼의 크기입니다.  
  
 `pcbData`  
 [out] 반환 된 바이트 수를 반환 합니다. 하는 경우 `data` 됩니다 `NULL`, 다음 `pcbData` 사용할 수 있는 데이터의 바이트의 총 수를 포함 합니다.  
  
 `data`  
 [out] 지정된 된 위치에서 데이터를 채울 수 있는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)



