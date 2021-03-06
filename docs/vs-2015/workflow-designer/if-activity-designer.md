---
title: 경우 활동 디자이너 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: fee98f4b95d626e429662d20501541c3241a9b2e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49244233"
---
# <a name="if-activity-designer"></a>If 활동 디자이너
<xref:System.Activities.Statements.If> 활동은 조건을 평가하고 그 결과에 따라 활동을 실행합니다. 이 활동은 절차적 모델링 스타일의 프로그래밍을 사용하는 경우에 가장 유용합니다. 예를 들어 <xref:System.Activities.Statements.If> 활동 또는 <xref:System.Activities.Statements.Sequence> 활동 안에 <xref:System.Activities.Statements.Parallel> 활동이 중첩될 수 있습니다. <xref:System.Activities.Statements.Flowchart> 활동을 사용 중인 경우 <xref:System.Activities.Statements.FlowDecision> 활동을 대신 사용해 보세요.  
  
## <a name="if-properties-in-the-workflow-designer"></a>Workflow Designer의 If 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.If> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.If.Condition%2A>|True|실행할 자식 활동을 결정하는 조건입니다. 설정 하는 <xref:System.Activities.Statements.If.Condition%2A>을 입력 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 식에는 **조건** 상자에 **경우** 활동 디자이너나 속성 표의.|  
|<xref:System.Activities.Statements.If.Else%2A>|False|경우에 실행할 활동입니다 합니다 <xref:System.Activities.Statements.If.Condition%2A> 됩니다 **false**합니다. 실행 되는 활동을 추가 하는 <xref:System.Activities.Statements.If.Else%2A> 분기에서의 활동를 **도구 상자** 에 **Else** 상자에 **경우** 힌트 텍스트가 있는 활동 디자이너 " 여기에 작업 놓기 "입니다.|  
|<xref:System.Activities.Statements.If.Then%2A>|False|경우에 실행할 활동입니다 합니다 <xref:System.Activities.Statements.If.Condition%2A> 됩니다 **true**합니다. 실행 되는 활동을 추가 하는 <xref:System.Activities.Statements.If.Then%2A> 분기에서의 활동를 **도구 상자** 에 **다음** 상자에 **경우** 힌트 텍스트가 있는 활동 디자이너 " 여기에 작업 놓기 "입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [시퀀스](../workflow-designer/sequence-activity-designer.md)   
 [병렬](../workflow-designer/parallel-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)