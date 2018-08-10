---
title: '방법: ClickOnce 게시 설정 버전 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, setting publish version
- publishing, ClickOnce
- Publish Version property
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c991975a369387fea248816f4465670f1062a927
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080228"
---
# <a name="how-to-set-the-clickonce-publish-version"></a>방법: ClickOnce 게시 설정 버전
합니다 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `Publish Version` 속성 게시 중인 응용 프로그램을 업데이트로 간주 됩니다 있는지 여부를 결정 합니다. 각 시간 버전 증가, 응용 프로그램 업데이트로 게시 됩니다.  
  
 `Publish Version` 속성에 설정할 수 있습니다 합니다 **게시** 페이지를 **프로젝트 디자이너**합니다.  
  
> [!NOTE]
>  자동으로 증가 하는 프로젝트 옵션은는 `Publish Version` 될 때마다 속성 응용 프로그램 게시;이 옵션은 기본적으로 사용 됩니다. 자세한 내용은 [방법: ClickOnce 게시 버전 자동 증가](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)합니다.  
  
### <a name="to-change-the-publish-version"></a>게시 버전을 변경 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭 합니다 **게시** 탭 합니다.  
  
3.  **게시 버전** 필드에 증가 합니다 **주요**, **부**, **빌드**, 또는 **수정** 버전 숫자입니다.  
  
    > [!NOTE]
    >  버전 번호를; 감소 되지 해야 따라서 이렇게 하면 예측할 수 없는 업데이트 동작을 일으킬 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)   
 [방법: 증분 ClickOnce 게시 버전 자동](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)