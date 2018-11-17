---
title: 'Idiastackwalkhelper:: Imageforva | Microsoft Docs'
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
- IDiaStackWalkHelper::imageForVA method
ms.assetid: 8d4edabf-3c01-4fef-8b61-4779f3371067
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a48891d39f79705e072196b52c0136aef64661c2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51740229"
---
# <a name="idiastackwalkhelperimageforva"></a>IDiaStackWalkHelper::imageForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

실행 파일의 메모리 공간에서 가상 주소 위치를 지정 하는 메모리에는 실행 파일 이미지의 시작 부분을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT imageForVA(  
   ULONGLONG  vaContext,  
   ULONGLONG *pvaImageStart  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `vaContext`  
 [in] 실행 파일의 공간에서 임의 위치에 있는 가상 주소입니다.  
  
 `pvaImageStart`  
 [out] 실행 파일의 이미지의 시작 가상 주소를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)



