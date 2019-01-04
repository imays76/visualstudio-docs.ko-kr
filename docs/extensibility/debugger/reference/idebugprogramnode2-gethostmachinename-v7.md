---
title: IDebugProgramNode2::GetHostMachineName_V7 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramNode2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramNode2::GetHostMachineName_V7
- IDebugProgramNode2::GetHostMachineNameIDebugProgramNode2::GetHostMachineName
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4518ab3e4a4ee978c296815a81d8fbffb3e20db7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53966653"
---
# <a name="idebugprogramnode2gethostmachinenamev7"></a>IDebugProgramNode2::GetHostMachineName_V7

> [!Note]
> 사용 되지 않습니다. 사용 하지 마세요.

## <a name="syntax"></a>구문

```cpp
HRESULT GetHostMachineName_V7 (
   BSTR* pbstrHostMachineName
);
```

```csharp
int GetHostMachineName_V7 (
   out string pbstrHostMachineName
);
```

#### <a name="parameters"></a>매개 변수

`pbstrHostMachineName`  
[out] 프로그램이 실행 중인 컴퓨터의 이름을 반환 합니다.

## <a name="return-value"></a>반환 값

구현을 항상 반환 `E_NOTIMPL`합니다.

## <a name="remarks"></a>설명

> [!WARNING]
> Visual Studio 2005를 기준으로이 메서드는 더 이상 및 항상 반환 `E_NOTIMPL`합니다.

## <a name="see-also"></a>참고 항목

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)