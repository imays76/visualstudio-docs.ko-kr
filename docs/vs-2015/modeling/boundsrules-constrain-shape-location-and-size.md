---
title: Boundsrules로 모양 위치 및 크기 제한 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, events
ms.assetid: 4d08e541-fc67-4e68-bf31-30d346aa2aa0
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: cb9d9c35f5600ee98d53863780d9f54c3eed53f4
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49253723"
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>BoundsRules로 모양 위치 및 크기 제한
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A *범위 규칙* 모양의 위치와 크기에 제한을 정의 하는 클래스입니다. 사용자가 셰이프 또는 모서리나 도형의 끌고 하는 동안 반복적으로 호출 되는 메서드를 제공 합니다.  
  
 다음 예제에서는 사각형 셰이프 고정 크기를 가로 또는 세로 막대 수를 제한 합니다. 사용자 모서리나 끌면 윤곽선 사이의 너비 및 높이의 두 가지 허용 된 구성은 대칭 이동 합니다.  
  
 범위 규칙 클래스에서 파생 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>합니다. 셰이프의 규칙의 인스턴스를 만듭니다.  
  
```  
using Microsoft.VisualStudio.Modeling.Diagrams; ...  
public partial class BarShape  
{  
  /// <summary>  
  /// Rule invoked when the user is resizing a shape.  
  /// </summary>  
  public override BoundsRules BoundsRules  
  { get { return new BarBoundsRule(); } }  
}  
/// <summary>  
/// Rule invoked when the user is changing a shape's outline.  
/// Provides real-time mouse rubber-band feedback, so must work fast.  
/// </summary>  
public class BarBoundsRule: BoundsRules  
{   
  public override RectangleD GetCompliantBounds   
     (ShapeElement shape, RectangleD proposedBounds)  
  {  
    double thickness = 0.1;  
    if (proposedBounds.Height > proposedBounds.Width)  
    {  
      // There is a minimum width for a shape; the width  
      // will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
            new SizeD(thickness, proposedBounds.Height));  
    }  
    else  
    {  
      // There is a minimum height for a shape; the   
      // height will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
         new SizeD(proposedBounds.Width, thickness));  
} } }  
```  
  
 확인 하려는 경우 위치 및 크기를 둘 다 수 제한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>   
 [변경 내용에 대한 대응 및 전파](../modeling/responding-to-and-propagating-changes.md)



