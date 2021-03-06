---
title: '방법: 데이터에 ListObject 열 매핑'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], mapping to ListObject column
- ListObject control, mapping data
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 508a0fa8df58e70eb216f722ee96395c7a9c21ad
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53899985"
---
# <a name="how-to-map-listobject-columns-to-data"></a>방법: 데이터에 ListObject 열 매핑
  <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 <xref:System.Data.DataTable>에 바인딩할 때 목록에 있는 모든 열이 표시되는 것을 원하지 않거나 데이터에 바인딩되지 않은 특정 열이 있을 수 있습니다. <xref:Microsoft.Office.Tools.Excel.ListObject> 메서드를 호출할 때 <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> 에 나타내려는 열을 매핑할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 관련된 비디오 데모를 참조 하세요. [어떻게 할까요? Excel에서 SharePoint 목록에 연결 된 목록 만들기 ](http://go.microsoft.com/fwlink/?LinkID=130263).  
  
## <a name="map-columns"></a>열 매핑  
  
### <a name="to-map-a-data-table-to-columns-in-a-list"></a>데이터 테이블을 목록의 열에 매핑하려면  
  
1.  클래스 수준에서 <xref:System.Data.DataTable> 을 만듭니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#16)]
     [!code-vb[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#16)]  
  
2.  샘플 열과 데이터를 추가 합니다 `Startup` 이벤트 처리기는 `Sheet1` 클래스 (문서 수준 프로젝트를) 또는 `ThisAddIn` 클래스 (VSTO 추가 기능 프로젝트를).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#17)]
     [!code-vb[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#17)]  
  
3.  <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> 메서드를 호출하고 표시할 순서대로 열 이름을 전달합니다. 목록 개체를 바인딩할 수는 새로 만들어진 <xref:System.Data.DataTable>, 목록 개체의 열 순서에 나타나는 순서와에서 다릅니다. 하지만 <xref:System.Data.DataTable>합니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#18)]
     [!code-vb[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#18)]  
  
## <a name="specify-unmapped-columns"></a>매핑되지 않은 열 지정  
 <xref:System.Data.DataTable>에 열을 매핑할 때 빈 문자열을 전달하여 특정 열이 데이터에 바인딩되지 않도록 지정할 수도 있습니다. 데이터에 바인딩되지 않은 새 열은 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤에 추가됩니다.  
  
### <a name="to-specify-an-unmapped-column-when-mapping-listobject-columns"></a>ListObject 열을 매핑할 때 매핑되지 않은 열을 지정하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> 메서드를 호출하고 표시할 순서대로 열 이름을 전달합니다. 빈 문자열을 사용하여 매핑되지 않은 열이 추가될 위치를 지정합니다. 이 경우 직책 열과 성 열 사이입니다.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#19)]
     [!code-vb[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#19)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 코드 예제에서는 이 코드가 표시되는 워크시트에 <xref:Microsoft.Office.Tools.Excel.ListObject> 이라는 기존 `list1` 가 있는 것으로 간주합니다.  
  
## <a name="see-also"></a>참고자료  
 [Word 문서 및 런타임에 VSTO 추가 기능에서 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [방법: ListObject 컨트롤을 데이터로 채우기](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject 컨트롤](../vsto/listobject-control.md)  
