---
title: IWefDebuggingSupport 인터페이스
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 73aff964cfb66d33e308aef6448fc0f0b1b27c09
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53901021"
---
# <a name="iwefdebuggingsupport-interface"></a>IWefDebuggingSupport 인터페이스
  Office 용 앱의 디버깅을 용이 하 게 Visual Studio와 같은 디버깅 환경에서 구현 합니다. Word 또는 Excel과 같은 Office 응용 프로그램을 Visual Studio에서이 인터페이스를 가져오고 디버깅 세션 중 특정 지점에서 인터페이스의 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```csharp 
[  
    uuid(ccaf1a90-ce1c-4199-9cd6-b40c5c57a671),  
    oleautomation  
]  
interface IWefDebuggingSupport : IUnknown  
{  
    HRESULT SetWefProcessId(  
        [in] DWORD dwProcessId);  
    HRESULT GetAutoInsertExtensions(  
        [out, retval] SAFEARRAY(BSTR)* psaExtensionNames);  
}  
```  
  
## <a name="methods"></a>메서드  
 다음 표에서 IWefDebuggingSupport 인터페이스를 정의 하는 메서드를 나열 합니다.  
  
|이름|설명|  
|----------|-----------------|  
|[GetAutoInsertExtensions 메서드](../vsto/getautoinsertextensions-method.md)|디버깅 하는 동안 자동으로 삽입 하는 Office 용 앱에 대 한 정보를 가져옵니다.|  
|[SetWefProcessId 메서드](../vsto/setwefprocessid-method.md)|웹 확장 프레임 워크 (WEF) 콘텐츠를 실행 하는 프로세스 식별자를 제공 합니다.|  
