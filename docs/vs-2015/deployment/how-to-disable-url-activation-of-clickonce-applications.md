---
title: '방법: ClickOnce 응용 프로그램의 URL 활성화 해제 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 47fc07ade4529ab99a4c687ea62791ec083d2d0b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49273333"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>방법: ClickOnce 응용 프로그램의 URL 활성화를 사용하지 않도록 설정
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

일반적으로 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 응용 프로그램은 웹 서버에서 설치된 후 바로 자동으로 시작됩니다. 보안상의 이유로이 동작을 사용 하지 않도록 설정 하 여 사용자가 응용 프로그램을 시작 하도록 설정할 수 있습니다 합니다 **시작** 메뉴 대신 합니다. 다음 절차에서는 URL 활성화를 사용하지 않도록 설정하는 방법에 대해 설명합니다.  
  
 이 방법은 웹 서버에서 사용자 컴퓨터에 설치된 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 응용 프로그램에 대해서만 사용할 수 있습니다. URL을 사용하여 시작할 수 있는 온라인 전용 응용 프로그램에는 사용할 수 없습니다. 참조 및 설치 된 온라인 전용 응용 프로그램 간의 차이점에 대 한 자세한 내용은 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)합니다.  
  
 이 절차에서는 [!INCLUDE[winsdklong](../includes/winsdklong-md.md)] 도구 MageUI.exe를 사용합니다. 이 도구에 대 한 자세한 내용은 참조 하세요. [MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)](http://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14)합니다. 또한 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]을(를) 사용하여 이 작업을 수행할 수 있습니다.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-disable-url-activation-for-your-application"></a>응용 프로그램의 URL 활성화를 사용하지 않도록 설정하려면  
  
1.  MageUI.exe에서 배포 매니페스트를 엽니다. 아직 만들지 않은 한의 단계를 따릅니다 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)합니다.  
  
2.  선택 된 **배포 옵션** 탭 합니다.  
  
3.  선택을 취소 합니다 **자동으로 설치한 후 응용 프로그램을 실행** 확인란 합니다.  
  
4.  매니페스트를 저장하고 여기에 서명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)



