---
title: IDebugSessionProvider 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugSessionProvider interface
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6d17546d5461a1ad76b144bf2652672ab4aa675
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345151"
---
# <a name="idebugsessionprovider-interface"></a>IDebugSessionProvider 인터페이스
디버거 호스트 및 언어를 사용 하도록 설정 하려면 IDE에서 제공 하는 기본 인터페이스 디버깅을 시작 합니다. 실행 중인 응용 프로그램에 대 한 디버그 세션을 설정합니다. 컴퓨터 디버그 관리자에서이 인터페이스를 구현 됩니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugSessionProvider` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|지정된 된 응용 프로그램을 사용 하 여 디버그 세션을 시작합니다.|