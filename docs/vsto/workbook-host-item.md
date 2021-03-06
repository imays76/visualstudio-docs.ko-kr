---
title: 통합 문서 호스트 항목
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel workbooks
- Workbook host items
- host items [Office development in Visual Studio], Workbook
- workbooks, Excel
- Workbook host items, events
- workbooks
- Excel [Office development in Visual Studio], workbooks
- workbooks, events
- events [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f15d93818c2db553d22d9639e6460f6637d33c80
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53952890"
---
# <a name="workbook-host-item"></a>통합 문서 호스트 항목
  <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 항목은 Excel용 주 interop 어셈블리의 <xref:Microsoft.Office.Interop.Excel.Workbook> 형식을 확장한 형식입니다. <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 항목은 <xref:Microsoft.Office.Interop.Excel.Workbook> 개체와 동일한 속성, 메서드 및 이벤트를 제공하지만 추가 기능도 제공합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 문서 수준 프로젝트에는 프로젝트의 통합 문서를 나타내는 기본 <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 항목이 있습니다. VSTO 추가 기능 프로젝트에서 생성할 수 있습니다 <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 런타임 시 항목입니다.  
  
## <a name="understand-the-workbook-host-item-in-document-level-projects"></a>문서 수준 프로젝트에서 통합 문서 호스트 항목 이해  
 프로젝트의 통합 문서에 액세스하려면 `ThisWorkbook` 클래스를 사용합니다. `ThisWorkbook` 클래스는 <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 항목의 멤버에 대한 액세스를 제공하여 통합 문서를 열거나 닫을 때 코드를 실행하는 등 사용자 지정에서 기본 작업을 수행합니다. 자세한 내용은 [문서 수준 사용자 지정 프로그램](../vsto/programming-document-level-customizations.md)합니다.  
  
 `ThisWorkbook` 클래스는 프로젝트에서 코드를 작성하기 시작할 수 있는 위치를 제공합니다. 이 클래스는 Excel용 주 interop 어셈블리의 <xref:Microsoft.Office.Interop.Excel.Workbook> 개체와 동일한 속성, 메서드 및 이벤트를 제공하므로 `ThisWorkbook` 을 사용하여 Excel의 개체 모델에 액세스할 수 있습니다. 자세한 내용은 [Excel 개체 모델 개요](../vsto/excel-object-model-overview.md)합니다.  
  
 **솔루션 탐색기** 에서 **ThisWorkbook** 프로젝트 항목을 두 번 클릭하면 통합 문서 디자이너가 표시되고 **속성** 창에 통합 문서의 속성 및 이벤트가 표시됩니다.  
  
### <a name="limitations-of-the-workbook-host-item-in-document-level-projects"></a>문서 수준 프로젝트에서 통합 문서 호스트 항목 제한  
 문서 수준의 프로젝트에는 하나의 <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 항목(즉, `ThisWorkbook` 클래스)만 포함할 수 있습니다. 새로 추가할 수 없습니다 <xref:Microsoft.Office.Tools.Excel.Workbook> 디자인 타임에 프로젝트에 호스트 항목 및 새를 만들 수 없습니다 <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트는 문서 수준 사용자 지정에서 런타임에 항목입니다.  
  
 형식의 됩니다 런타임에 새 Excel 통합 문서를 만든 경우 <xref:Microsoft.Office.Interop.Excel.Workbook>합니다. 이 형식은 호스트 항목이 아니므로 호스트 컨트롤 또는 Windows Forms 컨트롤을 포함할 수 없습니다. 런타임에 통합 문서를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 프로그래밍 방식으로 새 통합 문서를 만드는](../vsto/how-to-programmatically-create-new-workbooks.md)합니다.  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 항목은 호스트 컨트롤의 컨테이너로 사용되지 않습니다. 그러므로 통합 문서에 보이는 컨트롤을 추가할 수 없지만 <xref:System.Data.DataSet>등의 구성 요소는 추가할 수 있으므로 모든 워크시트에서 구성 요소를 공유할 수 있습니다. 도메인 수준 프로젝트에서 통합 문서에 사용할 수 있는 구성 요소는 **도구 상자** 의 **구성 요소** 탭, **데이터** 탭 및 **모든 Windows Forms**탭에서 찾을 수 있습니다.  
  
> [!NOTE]  
>  Visual Studio의 Office 개발 도구는 공유 통합 문서를 지원하지 않습니다.  
  
## <a name="understand-workbook-host-items-in-vsto-add-in-projects"></a>VSTO 추가 기능 프로젝트에서 통합 문서 호스트 항목 이해  
 VSTO 추가 기능 프로젝트에서 생성할 수 있습니다는 <xref:Microsoft.Office.Tools.Excel.Workbook> Excel에서 열려 있는 통합 문서에 대해 런타임에 호스트 항목입니다. <xref:Microsoft.Office.Tools.Excel.Workbook> 호스트 항목을 생성하려면 `GetVstoObject` 메서드를 사용합니다. 자세한 내용은 [확장 Word 문서 및 Excel 통합 런타임에 VSTO 추가 기능에서](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)합니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [Word 문서 및 런타임에 VSTO 추가 기능에서 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍 방식으로 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
