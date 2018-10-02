---
title: IDataObject에서 UML 모델 요소 가져오기 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML API, copy and paste
ms.assetid: e0b9cec8-3b93-4a24-8bd3-3e086501d387
caps.latest.revision: 20
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: a69a6f20fdccdce9d8795c68bf0a70c74604428b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555434"
---
# <a name="get-uml-model-elements-from-idataobject"></a>IDataObject에서 UML 모델 요소 가져오기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [가져올 모델 IDataObject에서에서 UML 요소](https://docs.microsoft.com/visualstudio/modeling/get-uml-model-elements-from-idataobject)합니다.  
  
사용자가 소스에서 다이어그램으로 요소를 끌어 오면 끌어 온 요소가 `System.Windows.Forms.IDataObject`에서 인코딩됩니다. 인코딩은 소스 개체 형식에 따라 다릅니다. 다음 조각에서는 소스가 UML 다이어그램일 때 요소를 검색하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  형식을 사용 하 여 UML 모델에서 수행 해야 하는 작업의 대부분을 수행할 수 있는 어셈블리에서 정의 **Microsoft.VisualStudio.Uml.Interfaces** 고  **Microsoft.VisualStudio.ArchitectureTools.Extensibility**합니다. 하지만 이 예제에서는 UML 모델링 도구 구현의 파트인 일부 클래스를 사용해야 합니다. 예를 들어 이 조각의 `ShapeElement`는 UML `IShape`와 같지 않습니다. UML 모델 및 다이어그램이 불일치 상태로 전환되는 위험을 줄이려면 대체 방법이 없는 경우를 제외하고 이들 구현 클래스에서 메서드를 사용하지 않는 것이 좋습니다.  
  
## <a name="code-sample"></a>코드 샘플  
 프로젝트는 다음을 참조 해야 [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)] 어셈블리:  
  
 **Microsoft.VisualStudio.Modeling.Sdk 합니다. [version]**  
  
 **Microsoft.VisualStudio.Modeling.Sdk.Diagrams 합니다. [version]**  
  
 **System.Windows.Forms**  
  
```  
using Microsoft.VisualStudio.Modeling;    
  // for ElementGroupPrototype  
using Microsoft.VisualStudio.Modeling.Diagrams;    
  // for ShapeElement, DiagramDragEventArgs, DiagramPointEventArgs  
…   
  /// <summary>  
  /// Retrieves UML IElements from drag arguments.  
  /// Works for drags from UML diagrams.  
  /// </summary>  
  private IEnumerable<IElement> GetModelElementsFromDragEvent  
                  (DiagramDragEventArgs dragEvent)  
  {  
     //ElementGroupPrototype is the container for  
     //dragged and copied elements and toolbox items.  
     ElementGroupPrototype prototype =  
        dragEvent.Data.  
        GetData(typeof(ElementGroupPrototype))  
                     as ElementGroupPrototype;  
     // Locate the originals in the implementation store.  
     IElementDirectory implementationDirectory =   
        dragEvent.DiagramClientView.Diagram.Store.ElementDirectory;  
  
     return  prototype.ProtoElements.Select(  
       prototypeElement =>   
       {  
          ModelElement element = implementationDirectory  
                .FindElement(prototypeElement.ElementId);  
          ShapeElement shapeElement = element as ShapeElement;  
          if (shapeElement != null)  
          {   
            // Dragged from a diagram.  
            return shapeElement.ModelElement as IElement;  
          }  
          else  
          {   
            // Dragged from UML Model Explorer.  
            return element as IElement;  
          }  
        });  
    }  
```  
  
 에 대 한 자세한 내용은 `ElementGroupPrototype` 및 `Store` 표시는 UML 모델링 도구가 구현 되 [Modeling SDK for Visual Studio-도메인별 언어](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [UML API를 사용한 프로그래밍](../modeling/programming-with-the-uml-api.md)   
 [모델링 다이어그램의 메뉴 명령 정의](../modeling/define-a-menu-command-on-a-modeling-diagram.md)



