---
title: Icon 요소 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Icon
- Icon element (VSCT XML schema)
ms.assetid: 73c58fe3-d53c-4f4e-b025-29567c6cbb7c
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d7c82d55425ccc732ddc5255642d889816810352
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51731515"
---
# <a name="icon-element"></a>Icon 요소
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

아이콘 태그의 guid 속성에 정의 된 비트맵의 guid입니다.  Id 특성 비트맵 스트립에 슬롯을 선택합니다. 이 요소는 선택적입니다.  이 요소를 생략 하면 변수의 **guidOfficeIcon:msotcidNoIcon** 암시 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Icon guid="guidImages" id="bmpPic1" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

