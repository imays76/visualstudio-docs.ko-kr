---
title: IDebugSymbolProviderDirect | Microsoft Docs
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
- IDebugSymbolProviderDirect interface
ms.assetid: 872b04a8-70de-4ab5-aceb-684c81828545
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0c0d8ea7a4d01b3fe18eccab67adfadb1a62cd75
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551894"
---
# <a name="idebugsymbolproviderdirect"></a>IDebugSymbolProviderDirect
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugSymbolProviderDirect](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsymbolproviderdirect)합니다.  
  
메타 데이터 및 core 기호 인터페이스에 직접 액세스할 수 있는 기호 공급자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugSymbolProviderDirect: IUnknown  
```  
  
## <a name="methods"></a>메서드  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAppIDFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getappidfromaddress.md)|디버그 주소를 지정 하는 응용 프로그램 도메인 식별자를 검색 합니다.|  
|[GetCurrentModulesInfo](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesinfo.md)|기호 그룹의 모듈에 대 한 정보를 검색합니다.|  
|[GetCurrentModulesState](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesstate.md)|기호 공급자 멤버인 기호 그룹에 대 한 정보를 검색 합니다.|  
|[GetMetaDataImport](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmetadataimport.md)|메타 데이터 가져오기 정보를 검색합니다.|  
|[GetMethodFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmethodfromaddress.md)|지정 된 디버그 주소에서 메서드에 대 한 정보를 검색합니다.|  
|[GetSymUnmanagedReader](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getsymunmanagedreader.md)|비관리 코드에 대 한 기호 판독기를 검색합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 대부분의 다른 기호 공급자 인터페이스 대신 사용할 수 있습니다. 메타 데이터에 직접 액세스를 제공 하 고 `CorSym` 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

