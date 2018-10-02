---
title: 'Idiaframedata:: Execute | Microsoft Docs'
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
- IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1f76bf5e5ef30c748f310e6a8a610035b7c08bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47544205"
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiaframedata:: Execute](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-execute)합니다.  
  
스택 해제를 수행 하 고 스택 워크 프레임 인터페이스에서 결과 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT execute (   
   IDiaStackWalkFrame* frame  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `frame`  
 [in] [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) 프레임 레지스터의 상태를 보유 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 다음 표에서이 메서드에 대 한 가능한 반환 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_DIA_INPROLOG|프롤로그 코드에서 스택 프레임을 실행할 수 없습니다.|  
|E_DIA_SYNTAX|프레임 프로그램에서 발생 한 오류를 구문 분석 합니다.|  
|E_DIA_FRAME_ACCESS|메모리 액세스 등록 수 없습니다.|  
|E_DIA_VALUE|값 (예: 0으로 나누기)의 계산에서 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 스택 해제를 디버깅 하는 동안 호출 됩니다. 합니다 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) 개체는 레지스터에 업데이트를 수신 하는 데 사용 되는 메서드를 제공 합니다. 클라이언트 응용 프로그램에 의해 구현 됩니다는 `execute` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)



