---
title: '방법: 프로그래밍 방식으로 전자 메일 보내기'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 91e59cc8d7bd0115a59c71f13e8e2dc200336b29
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53840423"
---
# <a name="how-to-programmatically-send-email"></a>방법: 프로그래밍 방식으로 전자 메일 보내기  
  이 예제에서는 도메인 이름을 가진 연락처에 전자 메일 메시지를 보냅니다 **example.com** 가 전자 메일 주소입니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예제  
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   도메인 이름을 가진 연락처 **example.com** 가 전자 메일 주소입니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 도메인 이름을 검색 하는 필터 코드를 제거 하지 마세요 **example.com**합니다. 필터를 제거 하는 경우 솔루션이 회원님 연락처의 모든 전자 메일 메시지를 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [메일 항목 작업](../vsto/working-with-mail-items.md)   
 [방법: 프로그래밍 방식으로 전자 메일 항목 만들기](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [방법: 프로그래밍 방식으로 Outlook 연락처 액세스](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [방법: 프로그래밍 방식으로 전자 메일 메시지를 받으면 작업을 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
