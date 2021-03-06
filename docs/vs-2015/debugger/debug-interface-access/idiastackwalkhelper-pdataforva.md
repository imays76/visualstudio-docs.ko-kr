---
title: IDiaStackWalkHelper::pdataForVA | Microsoft Docs
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
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c937ac3039ef5807623d99a9d7fcaadada17a3e6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816751"
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

가상 주소에 연결 된 PDATA 데이터 블록을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `va`  
 [in] 가져올 데이터의 가상 주소를 지정 합니다.  
  
 `cbData`  
 [in] 크기 (바이트)를 가져올 데이터입니다.  
  
 `pcbData`  
 [out] (바이트)를 가져온 데이터의 실제 크기를 반환 합니다.  
  
 `pbData`  
 [out에서] 요청된 된 데이터를 사용 하 여 입력 되는 버퍼입니다. 일 수 없습니다 `NULL`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 없습니다 PDATA 지정된 된 주소에 대 한 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 PDATA (".pdata" 라는 섹션 참조)는 컴파일 대상의 예외 처리 함수에 대 한 정보를 포함 합니다.  
  
 호출자가 호출자에 게 얼마나 많은 데이터를 사용할 수를 요청 하지 않아도 되므로 반환할 얼마나 많은 데이터를 알고 있습니다. 따라서 것이 오류를 반환 하는 경우이 메서드의 구현을 허용 되는 `pbData` 매개 변수는 `NULL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)



