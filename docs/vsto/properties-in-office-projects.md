---
title: Office 프로젝트의 속성
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Trust Assemblies Location property
- Cache in Document property
- properties [Office development in Visual Studio]
- Namespace for Host Item property
- Office projects [Office development in Visual Studio], properties
- projects [Office development in Visual Studio], properties
- Value2 property
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a3e2179d10983bc74c8dd9bb692f1eade44dec47
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53932222"
---
# <a name="properties-in-office-projects"></a>Office 프로젝트의 속성
  Visual Studio에서 Office 프로젝트에 사용할 수 있는 몇 가지 중요한 속성이 있습니다. 이러한 속성은 **속성** 창에서 액세스할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="namespace-for-host-item"></a>호스트 항목에 대 한 Namespace  
 Visual C# 프로젝트에서 **호스트 항목의 네임스페이스** 속성을 사용하여 호스트 항목 클래스(예: `ThisAddIn`, `ThisWorkbook`또는 `ThisDocument` 클래스)의 네임스페이스를 변경할 수 있습니다. 이 속성에 표시 됩니다는 **속성** 문서 수준 프로젝트의 문서 노드를 선택 하면 창 (같은 *ExcelWorkbook1.xlsx* 하거나 *WordDocument1.docx* )에서 VSTO 추가 기능 프로젝트에서 (예: Excel 또는 Word)에서 응용 프로그램 노드 **솔루션 탐색기**합니다.  
  
 Visual C# Office 프로젝트를 만들 때 프로젝트의 이름에 따라 호스트 항목에 네임스페이스가 제공됩니다. 코드 파일을 직접 편집하는 대신 **호스트 항목의 네임스페이스** 속성을 사용하여 네임스페이스를 변경하는 것이 좋습니다. 이 속성을 사용하는 경우 네임스페이스는 표시된 코드 파일뿐만 아니라 생성된(숨겨진) 코드 파일에서 변경됩니다.  
  
## <a name="cacheindocument"></a>CacheInDocument  
 **CacheInDocument** 속성은 Visual Studio 디자이너에서 **의 인스턴스를 선택할 때 문서 수준 프로젝트의** 속성 <xref:System.Data.DataSet> 창에 나타납니다. 공용 멤버만 캐시될 수 있습니다. **을 캐시하려는 경우** Modifiers **속성이** Public <xref:System.Data.DataSet>으로 설정되어 있는지 확인하세요.  
  
 이 속성은 부울 값을 사용합니다.  
  
- 문서에서 데이터 세트를 캐시하려면 **true**를 선택합니다.  
  
- 문서에서 데이터 세트를 캐시하지 않으려면 **false**를 선택합니다.  
  
  데이터를 캐시 하는 방법에 대 한 자세한 내용은 참조 하세요. [문서 수준 사용자 지정에서 캐시 된 데이터](../vsto/cached-data-in-document-level-customizations.md)입니다.  
  
## <a name="value2"></a>Value2  
 **Value2** 속성은 Excel 통합 문서 또는 서식 파일 프로젝트에만 사용할 수 있습니다. 이 속성은 워크시트 디자이너에서 **컨트롤을 선택할 때** 속성 **창에서** Databindings <xref:Microsoft.Office.Tools.Excel.NamedRange> 속성 노드 아래에 표시됩니다.  
  
 **속성** 창에서 **Value2** 속성을 사용하여 <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> 의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 속성을 데이터 원본의 필드에 바인딩할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션을 만들고 디자인](../vsto/designing-and-creating-office-solutions.md)   
 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)   
 [Office 프로젝트의 이벤트](../vsto/events-in-office-projects.md)  
