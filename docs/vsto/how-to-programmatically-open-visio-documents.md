---
title: '방법: 프로그래밍 방식으로 Visio 문서 열기'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening Visio documents
- Visio [Office development in Visual Studio], opening Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a3a7d2a9855abef0415661798c8a213eb748e22f
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257854"
---
# <a name="how-to-programmatically-open-visio-documents"></a>방법: 프로그래밍 방식으로 Visio 문서 열기
  기존 Microsoft Office Visio 문서를 여는 방법은 두 가지가 있습니다: 열고 OpenEx 합니다. OpenEx 메서드는 인수는 호출자에 게 문서가 열리는 방식을 지정할 수 있다는 점을 제외 하 고 Open 메서드가 동일 합니다.  
  
 개체 모델에 대한 자세한 내용은 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Documents.Open](https://msdn.microsoft.com/library/office/ff765240.aspx) 메서드 및 [Microsoft.Office.Interop.Visio.Documents.OpenEx](https://msdn.microsoft.com/library/office/ff767229.aspx) 메서드를 참조하세요.  
  
## <a name="open-a-visio-document"></a>Visio 문서 열기  
  
### <a name="to-open-a-visio-document"></a>Visio 문서를 열려면  
  
-   호출 된 `Microsoft.Office.Interop.Visio.Documents.Open` 메서드와 Visio 문서의 정규화 된 경로 제공 합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="open-a-visio-document-with-specified-arguments"></a>지정 된 인수를 사용 하 여 Visio 문서 열기  
  
### <a name="to-open-a-visio-document-as-read-only-and-docked"></a>Visio 문서를 읽기 전용 및 도킹하여 열려면  
  
-   호출을 `Microsoft.Office.Interop.Visio.Documents.OpenEx` 메서드를 Visio 문서의 정규화 된 경로 입력 하 고 사용 하려는 인수를 포함-이 경우, 도킹 및 읽기 전용입니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#6)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   명명 된 Visio 문서 `myDrawing.vsd` 라는 디렉터리에 있어야 합니다 `Test` 에 *My Documents* 폴더 (Windows XP 및 이전) 또는 *문서* 폴더 (Windows Vista).  
  
## <a name="see-also"></a>참고자료  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 새 Visio 문서 만들기](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 닫기](../vsto/how-to-programmatically-close-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 저장](../vsto/how-to-programmatically-save-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 인쇄](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  