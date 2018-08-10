---
title: Icon 요소 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Icon
- Icon element (VSCT XML schema)
ms.assetid: 73c58fe3-d53c-4f4e-b025-29567c6cbb7c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2494e75c312385a1a0c86709eb417d4b124a97de
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497695"
---
# <a name="icon-element"></a>Icon 요소
아이콘 태그의 guid 속성에 정의 된 비트맵의 guid입니다. `id` 특성 비트맵 스트립에 슬롯을 선택 합니다. 이 요소는 선택적입니다. 이 요소를 사용 하는 경우의 값이 포함 되었습니다 **guidOfficeIcon:msotcidNoIcon** 암시 됩니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<Icon guid="guidImages" id="bmpPic1" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|guid|필수. 정의 된 비트맵의 guid입니다.|  
|ID|필수. 비트맵 스트립에 슬롯을 선택합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|없음|없음|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Buttons 요소](../extensibility/buttons-element.md)||  
  
## <a name="see-also"></a>참고자료  
 [Visual Studio 명령 테이블 (.vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)