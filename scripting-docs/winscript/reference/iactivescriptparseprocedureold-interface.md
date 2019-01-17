---
title: IActiveScriptParseProcedureOld 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParseProcedureOld
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParseProcedureOld interface
ms.assetid: d94b391e-4c24-46da-a01f-2c134ca4f041
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa7ea909680afdb65004f47e458d735e82ead929
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349997"
---
# <a name="iactivescriptparseprocedureold-interface"></a>IActiveScriptParseProcedureOld 인터페이스
스크립트에 추가 하는 절차에 대 한 소스 코드 텍스트를 허용 합니다. VBScript와 같은 독립 제작 환경에 있지 않은 해석 된 스크립팅 언어에 대 한 대체 메커니즘을 제공 (이외의 `IActiveScriptParse` 또는 `IPersist*`) 스크립트 프로시저 네임 스페이스를 추가 합니다.  
  
> [!NOTE]
>  위해이 인터페이스는 사용 되지 않습니다는 `IActiveScriptParseProcedure` 인터페이스입니다.  
  
## <a name="methods"></a>메서드  
 상속 된 메서드 외에도 `IUnknown`, `IActiveScriptParseProcedureOld` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptParseProcedureOld::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedureold-parseproceduretext.md)|지정 된 코드 프로시저를 구문 분석 하 고 프로시저의 네임 스페이스에 추가 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)