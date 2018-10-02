---
title: 서버 (Visual Studio SDK) | Microsoft Docs
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
- servers, debugging
- debugging [Debugging SDK], servers
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e79e5e00bb4708359c19fd6a2ff95c7f31fd1179
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47565298"
---
# <a name="servers-visual-studio-sdk"></a>서버(Visual Studio SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [(Visual Studio SDK) 서버](https://docs.microsoft.com/visualstudio/extensibility/debugger/servers-visual-studio-sdk)합니다.  
  
디버거 아키텍처 측면을 **server**:  
  
-   포트 및 포트 공급 업체의 컨테이너 이며 세션 디버그 관리자 (SDM) 포트 및 포트 공급 업체와 통신 하 고 디버그 엔진에 사용 됩니다.  
  
-   이름별로 자신을 식별 하 고 해당 포트 및 포트 공급자를 열거할 수 있습니다.  
  
-   로 표시 됩니다는 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md) 만 Visual Studio (Visual Studio 실행의 각 인스턴스에 대해 서버 인스턴스 하나)에서 구현 되는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [포트](../../extensibility/debugger/ports.md)   
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)

