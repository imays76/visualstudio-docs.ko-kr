---
title: 속성 &lt;속성 이름이&gt; 삭제할 수 없습니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 98b065500c9c881a7190b59c4d70a0433eb8864c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49186526"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>속성 &lt;속성 이름이&gt; 삭제할 수 없습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
속성 \<속성 이름 > 간 상속의 판별자 속성으로 설정 되어 있으므로 삭제할 수 없습니다 \<클래스 이름 > 및 \<클래스 이름 >  
  
 선택한 속성이로 설정 되어는 **Discriminator Property** 오류 메시지에 표시 된 클래스 간 상속 합니다. 속성이 데이터 클래스 간 상속 구성에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.  
  
 설정 합니다 **Discriminator Property** desired 속성을 삭제할 수 있도록 데이터 클래스의 다른 속성에 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  O/R 디자이너에서 오류 메시지에 표시된 데이터 클래스를 연결하는 상속 선을 선택합니다.  
  
2.  설정 된 **판별자** 속성을 다른 속성입니다.  
  
3.  속성 삭제를 다시 한 번 시도합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: O/R 디자이너를 사용 하 여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)   
 [데이터 클래스 상속 (O/R 디자이너)](../data-tools/data-class-inheritance-o-r-designer.md)   
 [연습: 단일 테이블 상속을 사용하여 LINQ to SQL 클래스 만들기(O/R 디자이너)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)

