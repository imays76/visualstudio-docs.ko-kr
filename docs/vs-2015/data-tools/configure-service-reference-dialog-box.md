---
title: 서비스 참조 구성 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 24da338378739afca6ad228582a29069aebde9f5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266983"
---
# <a name="configure-service-reference-dialog-box"></a>서비스 참조 구성 대화 상자
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
합니다 **서비스 참조 구성** 대화 상자를 사용 하는 동작을 구성할 수 있습니다 [!INCLUDE[vsindigo](../includes/vsindigo-md.md)] 서비스입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
 액세스 하는 **서비스 참조 구성** 에서 참조 대화 상자에서 서비스를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **서비스 참조 구성**합니다. 클릭 하 여 대화 상자를 액세스할 수도 있습니다는 **고급** 단추를 **서비스 참조 추가 대화 상자**합니다.  
  
## <a name="task-list"></a>작업 목록  
  
-   WCF 서비스가 호스팅되는 주소를 변경 하려면 새 주소를 입력 합니다 **주소** 필드입니다.  
  
-   WCF 클라이언트에서 클래스에 대 한 액세스 수준을 변경 하려면의 액세스 수준 키워드를 선택 합니다 **생성 된 클래스에 대 한 수준 액세스** 목록입니다.  
  
-   WCF 서비스의 메서드를 비동기적으로 호출 하려면 선택 합니다 **비동기 작업 생성** 확인란 합니다.  
  
-   메시지 계약 형식에서 WCF 클라이언트를 생성 하려면 선택 합니다 **항상 메시지 계약 생성** 확인란 합니다.  
  
-   목록 또는 사전 컬렉션 형식을 WCF 클라이언트를 지정 하려면에서 형식을 선택 합니다 **컬렉션 형식을** 및 **사전 컬렉션 형식** 나열 합니다.  
  
-   형식 공유를 사용 하지 않으려면 선택을 취소 합니다 **참조 된 어셈블리의 형식 재사용** 확인란 합니다. 참조 된 어셈블리의 하위 집합에 대해 형식 공유를 사용 하도록 설정 하려면 선택 합니다 **참조 된 어셈블리의 형식 재사용** 확인란을 선택 **지정된 된 어셈블리의 형식 재사용**, 원하는 선택 참조 된 **참조 된 어셈블리 목록**합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **주소**  
 서비스 참조가 서비스를 검색하는 웹 주소를 업데이트하는 데 사용됩니다. 예를 들어 개발 도중 서비스를 개발 서버에서 호스팅하다가 나중에 프로덕션 서버로 이동하여 주소를 변경해야 하는 경우가 이에 해당할 수 있습니다.  
  
> [!NOTE]
>  Address 요소 사용할 수 없는 경우는 **서비스 참조 구성** 대화 상자에서 표시 됩니다는 **서비스 참조 추가 대화 상자**합니다.  
  
 **생성 된 클래스에 대 한 액세스 수준**  
 WCF 클라이언트 클래스에 대한 코드 액세스 수준을 결정합니다.  
  
> [!NOTE]
>  웹 사이트 프로젝트의 경우 이 옵션은 항상 `Public`으로 설정되며 변경할 수 없습니다. 자세한 내용은 [서비스 참조 문제 해결](../data-tools/troubleshooting-service-references.md)합니다.  
  
 **비동기 작업 생성**  
 WCF 서비스 메서드를 동기적으로(기본값) 호출할지 아니면 비동기적으로 호출할지를 결정합니다.  
  
 **작업 기반 작업 생성**  
 비동기 코드를 작성하는 경우 이 옵션을 사용하면 .Net 4에 도입된 TPL(작업 병렬 라이브러리)을 활용할 수 있습니다. 참조 [작업 병렬 라이브러리 (TPL)](http://msdn.microsoft.com/library/dd460717.aspx)합니다.  
  
 **항상 메시지 계약 생성**  
 WCF 클라이언트에 대해 메시지 계약 형식을 생성할지 여부를 결정합니다. 메시지 계약에 대 한 자세한 내용은 참조 하세요. [Using Message Contracts](http://msdn.microsoft.com/library/1e19c64a-ae84-4c2f-9155-91c54a77c249)합니다.  
  
 **컬렉션 형식**  
 WCF 클라이언트에 대한 목록 컬렉션 형식을 지정합니다. 기본 형식은 <xref:System.Array>입니다.  
  
 **사전 컬렉션 형식**  
 WCF 클라이언트에 대한 사전 컬렉션 형식을 지정합니다. 기본 형식은 <xref:System.Collections.Generic.Dictionary%602>입니다.  
  
 **참조 된 어셈블리의 형식 재사용**  
 서비스가 추가 또는 업데이트되면 WCF 클라이언트에서 새 형식을 생성하는 대신 참조된 어셈블리에 이미 있는 형식을 다시 사용하도록 할지 여부를 결정합니다. 기본적으로 이 옵션은 선택되어 있습니다.  
  
 **모든 참조 된 어셈블리의 형식 재사용**  
 선택 하면 모든 형식에는 **참조 된 어셈블리 목록** 가능 하면 다시 사용 됩니다. 기본적으로 이 옵션이 선택됩니다.  
  
 **지정된 된 어셈블리의 형식 재사용**  
 선택한 형식만 선택 합니다 **참조 된 어셈블리 목록** 다시 사용 됩니다.  
  
 **참조 된 어셈블리 목록**  
 프로젝트 또는 웹 사이트의 참조된 어셈블리 목록을 포함합니다. 때 **지정된 된 어셈블리의 형식 재사용** 을 선택 하면 개별 어셈블리를 선택 하거나 지울 수 있습니다.  
  
 **웹 참조 추가**  
 표시 된 [NIB: 웹 참조 추가 대화 상자](http://msdn.microsoft.com/en-us/bdf05776-c591-40af-bfd7-e1e2aa1e87b5)합니다.  
  
> [!NOTE]
>  이 옵션은 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 2.0 버전을 대상으로 하는 프로젝트에만 사용해야 합니다.  
  
> [!NOTE]
>  **웹 참조 추가** 단추를 사용할 수 있는 경우에만 합니다 **서비스 참조 구성** 에서 대화 상자가 표시 됩니다는 **서비스 참조 추가 대화 상자**.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 추가, 업데이트 또는 서비스 참조를 제거 합니다.](http://msdn.microsoft.com/library/cacc14bd-4455-4a44-be78-d2ac16113dd9)   
 [방법: 웹 서비스에 대 한 참조를 추가 합니다.](http://msdn.microsoft.com/library/952e49a1-567e-4a74-8cd7-f2e7b62c3168)   
 [Windows Communication Foundation 서비스 및 WCF Data Services](../data-tools/configure-service-reference-dialog-box.md)

