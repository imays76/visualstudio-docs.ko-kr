---
title: '방법: 실행 취소 스택을 지웁니다. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 75b821a757f466045b27b7f52e1900ece3f0b0d2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555923"
---
# <a name="how-to-clear-the-undo-stack"></a>방법: 실행 취소 스택을 지웁니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 실행 취소 스택을 지웁니다.](https://docs.microsoft.com/visualstudio/extensibility/how-to-clear-the-undo-stack)합니다.  
  
아래에 다음 프로시저 실행 취소 스택을 지웁니다. 하는 방법에 설명 합니다.  
  
### <a name="to-clear-the-undo-stack"></a>실행 취소 스택을 지웁니다.  
  
1.  실행 취소 스택을 사용의 선택을 취소 하는 [IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799) 메서드. 다음은이 예제입니다.  
  
    ```  
    HRESULT CCmdWindow::ClearUndoStack()  
    {  
      HRESULT hr = S_OK;  
  
      if (m_pUndoMgr == NULL)  
        {  
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));  
        ASSERT(m_pUndoMgr != NULL, "",;);  
        }  
  
      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));  
  
    Error:  
      return hr;  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)

