---
title: '방법: SharePoint 웹 파트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6437620b4215726ba48ea3234e37c76e77d21ebe
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37119838"
---
# <a name="how-to-create-a-sharepoint-web-part"></a>방법: SharePoint 웹 파트 만들기
  만들고 추가 하 여 웹 파트를 사용자 지정할 수 있습니다는 **웹 파트** SharePoint 프로젝트 항목 및 다음 웹 파트 또는 디자이너를 사용 하 여 코드 파일을 편집 합니다. 자세한 내용은 [방법: 디자이너를 사용 하 여 SharePoint 웹 파트를 만들](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)합니다.  
  
### <a name="to-create-a-sharepoint-web-part"></a>SharePoint 웹 파트를 만들려면
  
1.  SharePoint 프로젝트를 만들거나 엽니다.  
  
     자세한 내용은 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)합니다.  
  
2.  SharePoint 프로젝트 노드를 선택 **솔루션 탐색기** 를 선택한 후 **프로젝트** > **새 항목 추가**합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 합니다 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  SharePoint 템플릿의 목록에서 선택 **웹 파트**합니다.  
  
5.  에 **이름** 상자, 웹 파트에 대 한 이름을 지정 하 고 선택한 합니다 **추가** 단추입니다.  
  
     웹 파트에 나타납니다 **솔루션 탐색기**합니다. 웹 파트를 포함 하는 파일에 대 한 자세한 내용은 참조 하세요. [for SharePoint 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)합니다.  
  
6.  **솔루션 탐색기**, 방금 만든 웹 파트에 대 한 코드 파일을 엽니다.  
  
     예를 들어 웹 파트의 이름은 *WebPart1*오픈 *WebPart1.vb* (Visual Basic)에서는 또는 *WebPart1.cs* (C#에서).  
  
7.  코드 파일에서 <xref:System.Web.UI.Control.CreateChildControls%2A> 메서드에 컨트롤을 추가합니다.  
  
     예를 들어 참조 [연습: SharePoint에 대 한 웹 파트를 만드는](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)합니다.  
  
## <a name="see-also"></a>참고자료
 [SharePoint 용 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [방법: 디자이너를 사용 하 여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [연습: SharePoint 용 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)   
 [연습: 디자이너를 사용 하 여 SharePoint 용 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  
