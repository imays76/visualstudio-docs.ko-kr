---
title: VSG_NODEFAULT_INSTANCE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a5422cf4899e68a913e6cf15e4923da564859653
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53922575"
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
기본 인스턴스에 있는지 여부를 존재로 정의 된 [VsgDbg 클래스](vsgdbg-class.md) 클래스-프로그래밍 캡처 인터페이스를 제공 하는-제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## <a name="value"></a>값  
 존재 여부가 `VsgDbg` 클래스의 기본 인스턴스가 제공되는지 여부를 결정하는 전처리기 기호입니다. 이 기호가 정의된 경우 `VsgDbg` 클래스의 기본 인스턴스가 제공되지 않습니다. 그렇지 않으면 기본 인스턴스는 제공되고 프로그램을 실행하기 전에 초기화됩니다.  
  
 프로그래밍 캡처 인터페이스는 전역 범위 `g_pVsgDbg`를 사용하는 포인터를 통해 제공됩니다.  
  
```cpp
VsgDbg *g_pVsgDbg;  
```  
  
## <a name="remarks"></a>주의  
 기본 인스턴스는 대개 충분하지만 D3D 장치가 DLL 외부에서 생성되었을 때 DLL 내부에 프로그래밍 캡처 인터페이스를 사용하려면 `VsgDbg` 클래스의 자체 인스턴스를 만들고 관리해야 합니다. 이러한 방식으로 프로그래밍 캡처 API에 대한 자체 인터페이스를 관리하는 경우 오버헤드가 발생하지 않도록 `VSG_NODEFAULT_INSTANCE`를 정의하여 기본 인스턴스를 사용하지 않도록 설정합니다.  
  
 기본 인스턴스를 사용하지 않도록 설정된 경우 프로그램이 실행되기 전에 자동으로 초기화되고 프로그램이 끝나면 자동으로 제거됩니다. 이 인스턴스를 명시적으로 초기화하거나 초기화를 취소하지 않아도 됩니다.  
  
 기본 인스턴스를 사용 하지 않으려면 정의 해야 합니다 `VSG_NODEFAULT_INSTANCE` 포함 하기 전에 `vsgcapture.h` 프로그램에서 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 기본 인스턴스를 사용하지 않도록 설정하는 방법을 보여줍니다.  
  
```cpp
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```
