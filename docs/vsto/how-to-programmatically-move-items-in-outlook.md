---
title: '방법: 프로그래밍 방식으로 Outlook에서 항목 이동'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], moving items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 51123937fd26b6d6decf3770affd83b1d58d5bfc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875743"
---
# <a name="how-to-programmatically-move-items-in-outlook"></a>방법: 프로그래밍 방식으로 Outlook에서 항목 이동
  읽지 않은 전자 메일 메시지를 이동 하는이 예제는 **받은 편지함** 라는 폴더로 **테스트**합니다. 단어가 포함 된 메시지 이동 **테스트** 에 `Subject` 필드입니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예제  
 [!code-csharp[Trin_OL_MoveItems#1](../vsto/codesnippet/CSharp/Trin_OL_MoveItems/thisaddin.cs#1)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   명명 된 Outlook 메일 폴더 **테스트**합니다.  
  
-   단어를 사용 하 여 도착 하는 전자 메일 메시지 **테스트** 에 `Subject` 필드입니다.  
  
## <a name="see-also"></a>참고자료  
 [폴더 작업](../vsto/working-with-folders.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [방법: 프로그래밍 방식으로 특정 폴더 내용 검색](../vsto/how-to-programmatically-search-within-a-specific-folder.md)   
 [방법: 프로그래밍 방식으로 전자 메일 메시지를 받으면 작업을 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
