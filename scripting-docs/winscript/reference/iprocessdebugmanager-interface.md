---
title: IProcessDebugManager 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IProcessDebugManager interface
ms.assetid: b6ecb2bd-a4d1-4857-9232-036c154d0cb1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5feb67b1a616eeaa855b27cb12ea9b3146545ebd
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345125"
---
# <a name="iprocessdebugmanager-interface"></a>IProcessDebugManager 인터페이스
프로세스 디버그 관리자에 대한 기본 인터페이스입니다. 이 인터페이스는 프로세스에서 가상 애플리케이션을 작성, 추가 또는 제거할 수 있습니다. 이 스택 프레임 및 응용 프로그램 스레드 열거할 수 있습니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IProcessDebugManager` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IProcessDebugManager::CreateApplication](../../winscript/reference/iprocessdebugmanager-createapplication.md)|이 응용 프로그램에 대 한 새 디버그 응용 프로그램 개체를 만듭니다.|  
|[IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)|현재 프로세스에 대 한 기본 응용 프로그램 개체를 반환합니다.|  
|[IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)|컴퓨터 디버그 관리자의 목록에 응용 프로그램을 실행 하는 응용 프로그램을 추가 합니다.|  
|[IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)|실행 중인 응용 프로그램을 제거 합니다. 응용 프로그램 목록입니다.|  
|[IProcessDebugManager::CreateDebugDocumentHelper](../../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md)|이 응용 프로그램에 대 한 새 디버그 문서 도우미를 만듭니다.|