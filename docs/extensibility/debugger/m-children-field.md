---
title: m_children 필드 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a5d924e0439be2f8ab615d18a61f1303994b8dde
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53923694"
---
# <a name="mchildren-field"></a>m_children 필드
이 작업을 사용 하 여 등록 된 자식 작업의 목록입니다.  
  
 **네임스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (에서 *mscorlib.dll*)  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없는 때문에 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```csharp 
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>설명  
 작업이 실행 되는 동안 작업을 실행 하는 스레드만이 배열을 액세스 해야 합니다.  
  
 작업이 완료 되는 경우에 다른 스레드가에 아무것도 추가 하거나 아무 것도를 제거 하지는이 필드에 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [ContingentProperties 클래스](../../extensibility/debugger/contingentproperties-class-internal-members.md)