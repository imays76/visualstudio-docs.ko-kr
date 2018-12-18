---
title: '방법: 프로그래밍 방식으로 워크시트 인쇄'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- worksheets, printing
- print preview, worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c1e473baccd6e4bb4de1c36d8888082baf40034b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49876644"
---
# <a name="how-to-programmatically-print-worksheets"></a>방법: 프로그래밍 방식으로 워크시트 인쇄
  통합 문서의 모든 워크시트를 인쇄할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="print-a-worksheet-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 워크시트 인쇄  
  
### <a name="to-print-a-worksheet"></a>워크시트를 인쇄하려면  
  
1. `Sheet1`의 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintOut%2A> 메서드를 호출하고, 두 복사본을 요청하고, 인쇄 전에 문서를 미리 봅니다.  
  
    [!code-csharp[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#22)]
    [!code-vb[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#22)]  
  
   합니다 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> 메서드를 사용 하면에서 지정된 된 개체를 표시 하는 **인쇄 미리 보기** 창. 다음 코드에서는 `Sheet1`이라는 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목이 있다고 가정합니다.  
  
### <a name="to-preview-a-page-before-printing"></a>인쇄 전에 페이지를 미리 보려면  
  
1.  워크시트의 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#23)]  
  
## <a name="print-a-worksheet-in-a-vsto-add-in"></a>VSTO 추가 기능에서 워크시트 인쇄  
  
### <a name="to-print-a-worksheet"></a>워크시트를 인쇄하려면  
  
1. 활성 워크시트의 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintOut%2A> 메서드를 호출하고, 두 복사본을 요청하고, 인쇄 전에 문서를 미리 봅니다.  
  
    [!code-csharp[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#14)]
    [!code-vb[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#14)]  
  
   합니다 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> 메서드를 사용 하면에서 지정된 된 개체를 표시 하는 **인쇄 미리 보기** 창.  
  
### <a name="to-preview-a-page-before-printing"></a>인쇄 전에 페이지를 미리 보려면  
  
1.  활성 워크시트의 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>참고자료  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트에서 맞춤법 검사](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [Office 프로젝트의 개체에 대 한 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  