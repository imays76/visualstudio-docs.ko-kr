---
title: VSCodeWindow 개체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b9ef7d4b190a9b2c1a487fb70df33726ca9b3ed4
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586276"
---
# <a name="vscodewindow-object"></a>VSCodeWindow 개체
코드 창에는 일반적으로 하나 이상의 텍스트 뷰를 포함할 수 있는 특수 문서 창입니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체입니다.  
  
 아키텍처 측면에서 코드 창에는 창 프레임 내에 있는 문서 창이입니다. 기능적으로 코드 창에는 추가 기능을 사용 하 여 문서 창 단순히입니다. (MDI) 다중 문서 인터페이스 모드로 코드 MDI 자식 프레임입니다. 자세한 내용은 [레거시 API를 사용 하 여 코드 창을 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)합니다.  
  
 다음 표에서 인터페이스를 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> 개체입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|전역적으로 고유 식별자 (GUID)를 식별 하는 서비스를 찾으려면 일반 액세스 메커니즘을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|하나 이상의 코드 보기를 포함 하는 여러 문서 MDI (인터페이스) 자식을 나타냅니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|창 프레임을 채웁니다.|  
  
## <a name="see-also"></a>참고자료  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [그림 편집](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)