---
title: 속성 창에서 속성 값 업데이트 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, updating property values
- property values, updating in Properties window
ms.assetid: 9358e8c3-b9d2-4fd4-aaab-cf48d1526db4
caps.latest.revision: 9
manager: douge
ms.openlocfilehash: 0272ba348e29fb1a2a118a0ff4b0989a2aa1683f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551028"
---
# <a name="updating-property-values-in-the-properties-window"></a>속성 창에서 속성 값을 업데이트합니다.
**속성** 창이 속성 값 변경과 동기화 상태를 유지하도록 하는 방법에는 두 가지가 있습니다. 첫 번째 호출 하는 것은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 환경에서 제공 하는 도구 및 문서 창의 생성 및 액세스를 포함 하 여 기본 창 관리 기능에 대 한 액세스를 제공 하는 인터페이스입니다. 다음 단계에서 이 동기화 프로세스를 설명합니다.  
  
## <a name="updating-property-values-using-ivsuishell"></a>IVsUIShell을 사용하여 속성 값 업데이트  
  
#### <a name="to-update-property-values-using-the-ivsuishell-interface"></a>IVsUIShell 인터페이스를 사용하여 속성 값을 업데이트하려면  
  
1.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> (통해 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 서비스) 언제 든 지 해당 VSPackages, 프로젝트 또는 편집기를 만들거나 도구 또는 문서 창을 열거 해야 합니다.  
  
2.  구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.RefreshPropertyBrowser%2A> 유지 하는 **속성** 프로젝트에 대 한 속성 변경과 동기화 창 (또는 된 다른 개체에서 검색 되는 **속성** 창) 구현하지않고<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 발생 하 고 <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink.OnChanged%2A> 이벤트입니다.  
  
3.  구현 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.AdviseHierarchyEvents%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.UnadviseHierarchyEvents%2A> 설정 하 고 사용 하지 않도록 설정, 각각 구현 하는 계층 구조 필요 없이 계층 이벤트의 클라이언트 알림을 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>합니다.  
  
## <a name="updating-property-values-using-iconnection"></a>IConnection을 사용하여 속성 값 업데이트  
 **속성** 창과 속성 값 변경의 동기화를 유지하는 두 번째 방법은 연결 가능 개체에 `IConnection` 를 구현하여 송신 인터페이스가 있음을 나타내는 것입니다. 속성 이름을 지역화 하려는 경우에서 개체를 파생 <xref:System.ComponentModel.ICustomTypeDescriptor>합니다. <xref:System.ComponentModel.ICustomTypeDescriptor> 구현에서 반환 속성 설명자를 수정 하 고 속성의 이름을 변경할 수 있습니다. 설명을 지역화 하려면에서 파생 되는 특성을 만들려면 <xref:System.ComponentModel.DescriptionAttribute> Description 속성을 재정의 합니다.  
  
#### <a name="considerations-in-implementing-the-iconnection-interface"></a>IConnection 인터페이스 구현 시 고려 사항  
  
1.  `IConnection` 통해 열거자 하위 개체에 대 한 액세스를 제공 합니다 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> 인터페이스입니다. 모든 연결 지점 하위 개체에 대 한 액세스도 제공 구현 하는 각는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 인터페이스입니다.  
  
2.  모든 찾아보기 개체가 구현 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink> 이벤트입니다. **속성** 창은 `IConnection`를 통해 설정된 이벤트에 대해 통지합니다.  
  
3.  연결 지점 구현에서 허용 연결 수 (하나 이상)을 제어 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A>입니다. 하나의 인터페이스만 허용 하는 연결점을 반환할 수 있습니다 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> 에서 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.EnumConnections%2A> 메서드.  
  
4.  클라이언트가 호출할 수는 `IConnection` 통해 열거자 하위 개체에 대 한 액세스를 얻기 위해 인터페이스는 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> 인터페이스입니다. <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> 인터페이스 각 송신 인터페이스 ID (IID)에 대 한 연결점을 열거할 호출할 수 있습니다.  
  
5.  `IConnection` 사용 하 여 연결점 하위 개체에 대 한 액세스를 가져오려고 호출할 수도 있습니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 각 송신 IID에 대 한 인터페이스입니다. 통해를 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 인터페이스, 클라이언트를 시작 하거나 연결 가능한 개체 및 클라이언트 자체 동기화로 통지 루프를 종료 합니다. 클라이언트가 호출할 수도 합니다 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 인터페이스를 사용 하 여 열거자 개체를 가져오는 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnections> 알고 있는 연결을 열거 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 창 선택 영역 추적 발표](../misc/announcing-property-window-selection-tracking.md)   
 [속성 확장](../extensibility/internals/extending-properties.md)