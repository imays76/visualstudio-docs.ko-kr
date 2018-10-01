---
title: 데이터를 저장 하기 전에 데이터 바인딩된 컨트롤에서 in-process 편집 커밋 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- commiting edited records
- data-bound controls, in-process edits
- DataBinding class, commiting edited records
- hierarchical update, commiting edited records
- BindingSource class, commiting edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bd56f9acfce7933d0bc89e7e86eb8083b9b1f867
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549900"
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>데이터 바인딩된 컨트롤에서 데이터를 저장하기 전에 In-Process 편집 커밋
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [데이터를 저장 하기 전에 데이터 바인딩된 컨트롤에서 in-process 편집 커밋](https://docs.microsoft.com/visualstudio/data-tools/commit-in-process-edits-on-data-bound-controls-before-saving-data)합니다.  
  
  
데이터 바인딩된 컨트롤에서 값을 편집할 때 사용자가 컨트롤에 바인딩되는 데이터 원본에 값이 업데이트를 적용 하려면 현재 레코드 탐색 해야 합니다. 항목을 끌면 합니다 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) 폼으로 끌어 놓으면 첫 번째 항목에는 코드를 생성 합니다 **저장** 단추 클릭 이벤트에는 <xref:System.Windows.Forms.BindingNavigator>합니다. 이 코드는 호출을 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드는 <xref:System.Windows.Forms.BindingSource>합니다. 따라서 호출을 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드가 첫 번째에 대해서만 생성 됩니다 <xref:System.Windows.Forms.BindingSource> 폼에 추가 된 합니다.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 호출은 현재 편집 중인 데이터 바인딩된 컨트롤에서 진행 중인 모든 변경 내용을 커밋합니다. 따라서 데이터 바인딩된 컨트롤에 있는 경우 여전히 포커스 클릭 하면 합니다 **저장** 단추를 보류 중인 모든 편집 컨트롤 실제 저장 전에 커밋된에 (의 `TableAdapterManager.UpdateAll` 메서드).  
  
 사용자가 저장의 일부로 변경 내용을 커밋하지 않고 데이터를 저장 하려고 하는 경우에 자동으로 변경 내용을 커밋 하도록 응용 프로그램을 구성할 수 있습니다 프로세스입니다.  
  
> [!NOTE]
>  디자이너에 추가 된 `BindingSource.EndEdit` 첫 번째 항목에 대해서만 코드를 폼으로 삭제 합니다. 따라서 호출 하는 코드 줄을 추가 해야 합니다 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 각각에 대 한 메서드 <xref:System.Windows.Forms.BindingSource> 양식의 합니다. 호출 하는 코드 줄을 수동으로 추가할 수 있습니다 합니다 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 각각에 대 한 메서드 <xref:System.Windows.Forms.BindingSource>합니다. 추가할 수 있습니다는 `EndEditOnAllBindingSources` 메서드를 폼 및 저장을 수행 하기 전에 호출 됩니다.  
  
 다음 코드에서는 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) 모든 반복 하는 쿼리 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 호출 합니다 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드 각각에 대 한 <xref:System.Windows.Forms.BindingSource> 양식의 합니다.  
  
## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>EndEdit 양식의 모든 BindingSource 구성 요소에 대 한 호출  
  
1.  다음 코드를 포함 하는 폼에 추가 된 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#1)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#1)]  
  
2.  폼의 데이터를 저장 하는 호출 바로 전에 코드의 다음 줄을 추가 (의 `TableAdapterManager.UpdateAll()` 메서드).  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#2)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [계층적 업데이트](../data-tools/hierarchical-update.md)

