---
title: '방법: 프로그래밍 방식으로 워크시트 메모 표시'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, comments
- comments, worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e8f4875e75562d9fa1f6d9cd4982ae2148e35a1c
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257688"
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>방법: 프로그래밍 방식으로 워크시트 메모 표시
  Microsoft Office Excel 워크시트에서 프로그래밍 방식으로 메모를 표시하고 숨길 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 워크시트에 모든 메모를 표시하려면  
  
1.  메모를 표시하려는 경우 <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> 속성을 **true** 로 설정하고 그렇지 않은 경우 **false**로 설정합니다. 이 코드는 `ThisWorkbook` 클래스가 아니라 시트 클래스에 배치해야 합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]  
  
## <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>응용 프로그램 수준 VSTO의 추가 기능에서 워크시트에 모든 메모를 표시하려면  
  
1.  메모를 표시하려는 경우 <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> 속성을 **true** 로 설정하고 그렇지 않은 경우 **false**로 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]  
  
## <a name="see-also"></a>참고자료  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 추가 하 고 워크시트 메모를 삭제 합니다.](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
  