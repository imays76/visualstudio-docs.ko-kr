---
title: 바인딩 대화 상자 컨트롤을 사용자 지정 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.datasource.datauicustomization
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- Customize Control Binding dialog box
ms.assetid: abcc0be3-a18e-4f47-b354-d6b0c618e087
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 4d47fe3962651db91dcfdf6e59653db539a9f44b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552118"
---
# <a name="customize-control-binding-dialog-box"></a>컨트롤 바인딩 사용자 지정 대화 상자
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

사용 된 **컨트롤 바인딩 사용자 지정** 항목에 사용 가능한 컨트롤을 지정 하려면 대화 상자를 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)합니다.  
  
 각 항목에는 **데이터 원본** 창에는 연결 된 목록 항목에 바인딩되는 컨트롤입니다. 각 항목에 대해 사용할 수 있는 컨트롤 항목의 데이터 형식에 의해 결정 됩니다. 각 데이터 형식에 기본 컨트롤을 포함 하 여이 대화 상자에서 정의 하는 유효한 연결 된 컨트롤의 목록입니다.  
  
 데이터 바인딩된 컨트롤을 만드는 디자인 화면에 항목을 끌기 전에 만들 컨트롤을 선택할 수 있습니다. 항목을 끌면 합니다 **데이터 원본** 선택한 항목의 데이터 형식이 디자인 화면에 추가 됩니다에 대 한 기본 컨트롤 컨트롤을 선택 하지 않고 디자인 화면으로 창입니다.  
  
 항목에 대 한 컨트롤의 목록을 사용자 지정 하려면이 대화 상자를 사용 하는 방법에 대 한 자세한 합니다 **데이터 원본** 창 참조 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **데이터 형식**  
 컨트롤을 사용 하 여 연결 하는 형식의 목록을 표시 합니다.  
  
-   테이블, 엔터티 및 개체 라고 **[목록]** 형식입니다.  
  
-   엔터티 및 개체의 공용 속성 또는 열은 열 또는 내부 데이터 저장소에서 속성의 실제 데이터 형식으로 표시 됩니다.  
  
-   사용자 정의 셰이프를 사용 하 여 개체로 표시 됩니다 **[기타]** 합니다. 예를 들어, 응용 프로그램에 경우 개체의 속성이 둘 이상에서 데이터를 표시 하는 사용자 지정 컨트롤을 선택 합니다 **[기타]** 컨트롤에 대 한 데이터 형식입니다.  
  
 **연결 된 컨트롤**  
 특정 데이터 형식을 사용 하 여 연결할 수 있는 컨트롤의 목록을 표시 합니다. 특정 컨트롤에서 선택한 데이터 형식을 사용 하 여 연결 하려는 경우는 **데이터 형식** 목록에서 해당 확인란을 선택 합니다. 연결을 제거 하려면이 확인란의 선택을 취소 합니다. 제공한 바로 가기 메뉴에 컨트롤 표시를 확인 합니다 **데이터 원본** 연결 된 데이터 형식의 항목에 대 한 창.  
  
 여러 데이터 바인딩 특성 중 하나에 있는 컨트롤을 추가 하 여 목록에 컨트롤을 추가할 수 있습니다 합니다 **도구 상자**합니다. 자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.  
  
 **기본값 설정**  
 선택한 데이터 형식의 항목에 대 한 기본값이 되도록 선택한 컨트롤 형식을 할당 합니다. 제공한 바로 가기 메뉴의 첫 번째 선택 항목으로 표시 되는 기본 컨트롤을 **데이터 원본** 창 항목에 대 한 합니다. 데이터 형식에 대 한 기본값으로 하나의 컨트롤 형식을 할당할 수 있습니다.  
  
 **기본값 지우기**  
 선택한 데이터 형식에 대 한 기본 컨트롤의 지정을 제거합니다. 선택한 데이터 형식에 대 한 기본값이 없으면 **[없음]** 제공한 바로 가기 메뉴의 첫 번째 선택 항목으로 표시 됩니다는 **데이터 원본** 연결 된 형식의 항목에 대 한 창.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [새 데이터 소스 추가](../data-tools/add-new-data-sources.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)   
 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)