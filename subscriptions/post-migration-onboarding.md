---
title: 조직이 마이그레이션된 후 Visual Studio Subscription 관리 포털에 온보딩
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 07/12/2018
Ms.topic: Get-Started-Article
Description: Learn how to successfully onboard your organization for Visual Studio subscriptions after migrating to the administration portal.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: c6f0f3de58f2f9f7d532a7b1b84520644fbdb1c7
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39234797"
---
# <a name="onboarding-to-the-visual-studio-subscriptions-administration-portal-after-your-organization-was-migrated"></a>조직이 마이그레이션된 후 Visual Studio Subscription 관리 포털에 온보딩 

VLSC(볼륨 라이선스 서비스 센터)에서 Visual Studio Subscription을 관리했고 구독을 관리하기 위해 최근 사이트를 방문한 경우에는 VLSC에서 더 이상 구독 관리를 사용할 수 없음을 알 것입니다. 구독을 관리하는 프로세스는 다음과 같습니다.

![VLSC 구독](_img/post-migration-onboarding/vlsc-subscriptions.png)

구독 페이지에 도착하면 아래 링크를 클릭할 수 있습니다. 

![관계 요약 링크](_img/post-migration-onboarding/relationship-summary-link.png)

이 링크는 이전에는 구독을 관리할 수 있는 페이지로 이동하지 않았습니다.   그러나 이제 Visual Studio Subscription 관리 포털이라는 새 포털을 통해 구독을 관리합니다.  조직의 볼륨 라이선스 계약에 대한 주 또는 통지 연락처가 설정해야 하는 몇 가지 단계가 있습니다. 주 또는 통지 연락처가 이 프로세스를 완료하지 않거나 더 이상 사용할 수 없는 경우 발생할 수 있는 몇 가지 시나리오가 있습니다. 다음은 구독 관리에 대한 액세스 권한을 얻기 위해 수행할 단계를 안내합니다. 

다음과 같은 여러 가지 시나리오 중 하나가 발생할 수 있습니다.
1.  [주 연락처가 온보딩 프로세스를 완료하지 않은 경우](#Onboarding-not-completed-by-Primary-Contact)<sup>1</sup> 
2.  [주 연락처가 온보딩을 완료했지만 사용자를 관리자로 추가하지 않았고  자격 증명이 VLSC에 나열되어 있는 경우](#Primary-Contact-did-not-provide-you-administrator-access) 
3.  [주 연락처가 온보딩을 완료했지만 사용자를 관리자로 추가하지 않았고 자격 증명이 VLSC에 나열되어 있지 않은 경우](#Your-credentials-were-not-listed-in-VLSC-prior-to-migration)  

<sup>1</sup> 사용자가 주 또는 통지 연락처이고 온보딩 프로세스를 완료하지 않은 경우에는 조직을 설정하기 위해 시나리오 1의 단계를 수행해야 합니다. 

표시될 수 있는 화면의 예와 각 시나리오에 수행할 수 있는 단계는 다음과 같습니다. 

## <a name="onboarding-not-completed-by-primary-contact"></a>주 연락처가 온보딩을 완료하지 않은 경우

주 연락처가 온보딩 환경을 완료하지 않은 경우에는 아래 화면이 표시될 수 있습니다. [VLSC(볼륨 라이선스 서비스 센터)](https://www.microsoft.com/Licensing/servicecenter/default.aspx)에 액세스할 수 있는 경우 이 프로세스를 완료하고 구독을 관리할 권한을 얻을 수 있습니다. VLSC에서 찾을 수 있는 조직의 [PCN(공용 고객 번호)](find-pcn.md)이 필요합니다. 

주 연락처가 온보딩 프로세스를 완료하지 않은 경우에는 필드에 [PCN](find-pcn.md)을 입력하고 “초대 보내기”를 선택하면 됩니다. 

![초대 전자 메일 보내기](_img/post-migration-onboarding/send-invitation.png)

단추를 클릭하여 초대를 보낸 후 온보딩 프로세스를 완료하기 위한 고유한 링크가 포함된 전자 메일을 받습니다. 전자 메일에서 링크를 클릭하고, 전자 메일 주소로 로그인한 후, 다시 한번 PCN을 입력해야 합니다. 전자 메일의 고유한 링크를 통해 Visual Studio Subscription 관리 포털에 대한 액세스 권한을 얻을 수 있습니다. 그러면 구독에 액세스하여 구독을 관리할 수 있습니다. 

![전자 메일 성공](_img/post-migration-onboarding/email-success.png)


## <a name="primary-contact-did-not-provide-you-administrator-access"></a>주 연락처가 관리자 액세스 권한을 제공하지 않은 경우

주 연락처가 온보딩 프로세스를 완료했고 이전에 VLSC에 자격 증명이 있었지만 주 연락처가 액세스 권한을 제공하지 않은 경우에는 [Visual Studio Subscription 관리 포털](https://manage.visualstudio.com/)에 로그인할 때 다음 알림이 표시됩니다.  관리자가 되려면 화면에 나열된 조직의 슈퍼 관리자 중 한 명에게 문의해야 합니다.

![관리자 목록](_img/post-migration-onboarding/admin-list.png)

## <a name="your-credentials-were-not-listed-in-vlsc-prior-to-migration"></a>마이그레이션하기 전에 자격 증명이 VLSC에 나열되지 않은 경우

주 연락처가 온보딩을 완료했지만 사용자로 추가하지 않았고 자격 증명이 이전에 VLSC에 나열되지 않은 경우에는 [Visual Studio Subscription 관리 포털](https://manage.visualstudio.com/)에 액세스할 때 다음 알림이 표시됩니다. 포털에 대한 액세스 권한을 얻으려면 [주 연락처](find-primary-contact.md)에게 연락해야 합니다. 

![사용자를 찾을 수 없음](_img/post-migration-onboarding/cant-find-you.png)