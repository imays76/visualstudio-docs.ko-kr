---
title: 서비스 참조 구성 대화 상자
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 93d39aedc04cbdaebc35c892a8393ca394f44898
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281068"
---
# <a name="configure-service-reference-dialog-box"></a>서비스 참조 구성 대화 상자

합니다 **서비스 참조 구성** 대화 상자를 사용 하면 Windows Communication Foundation (WCF) 서비스의 동작을 구성할 수 있습니다.

> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

액세스 하는 **서비스 참조 구성** 에서 참조 대화 상자에서 서비스를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **서비스 참조 구성**합니다. 클릭 하 여 대화 상자를 액세스할 수도 있습니다는 **고급** 단추를 **서비스 참조 추가 대화 상자**합니다.

## <a name="task-list"></a>작업 목록

- WCF 서비스가 호스팅되는 주소를 변경 하려면 새 주소를 입력 합니다 **주소** 필드입니다.

- WCF 클라이언트에서 클래스에 대 한 액세스 수준을 변경 하려면의 액세스 수준 키워드를 선택 합니다 **생성 된 클래스에 대 한 수준 액세스** 목록입니다.

- WCF 서비스의 메서드를 비동기적으로 호출 하려면 선택 합니다 **비동기 작업 생성** 확인란 합니다.

- 메시지 계약 형식에서 WCF 클라이언트를 생성 하려면 선택 합니다 **항상 메시지 계약 생성** 확인란 합니다.

- 목록 또는 사전 컬렉션 형식을 WCF 클라이언트를 지정 하려면에서 형식을 선택 합니다 **컬렉션 형식을** 및 **사전 컬렉션 형식** 나열 합니다.

- 형식 공유를 사용 하지 않으려면 선택을 취소 합니다 **참조 된 어셈블리의 형식 재사용** 확인란 합니다. 참조 된 어셈블리의 하위 집합에 대해 형식 공유를 사용 하도록 설정 하려면 선택 합니다 **참조 된 어셈블리의 형식 재사용** 확인란을 선택 **지정된 된 어셈블리의 형식 재사용**, 원하는 선택 참조 된 **참조 된 어셈블리 목록**합니다.

## <a name="uielement-list"></a>UI 요소 목록

 **주소**

 웹 주소를 서비스에 대 한 서비스 참조를 찾을 위치를 업데이트 합니다. 예를 들어, 개발 하는 동안 서비스 수 개발 서버에서 호스트 되며 다음 나중에 주소 변경이 필요를 프로덕션 서버로 이동 합니다.

> [!NOTE]
> Address 요소 사용할 수 없는 경우는 **서비스 참조 구성** 대화 상자에서 표시 됩니다는 **서비스 참조 추가 대화 상자**합니다.

 **생성 된 클래스에 대 한 액세스 수준**

 WCF 클라이언트 클래스에 대한 코드 액세스 수준을 결정합니다.

> [!NOTE]
> 웹 사이트 프로젝트의 경우 이 옵션은 항상 `Public`으로 설정되며 변경할 수 없습니다. 자세한 내용은 [서비스 참조 문제 해결](../data-tools/troubleshooting-service-references.md)합니다.

 **비동기 작업 생성**

 WCF 서비스 메서드가 동기적으로 호출 되는지 여부를 결정 (기본값) 또는 비동기적으로 합니다.

 **작업 기반 작업 생성**

 비동기 코드를 작성할 때이 옵션의 작업 병렬 라이브러리 (TPL) 도입 된.NET 4를 사용 하 여 활용할 수 있습니다. 참조 [작업 병렬 라이브러리 (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl)합니다.

 **항상 메시지 계약 생성**

 WCF 클라이언트에 대 한 메시지 계약 형식을 생성 되는지 여부를 결정 합니다. 메시지 계약에 대 한 자세한 내용은 참조 하세요. [메시지 계약을 사용 하 여](/dotnet/framework/wcf/feature-details/using-message-contracts)입니다.

 **컬렉션 형식**

 WCF 클라이언트에 대한 목록 컬렉션 형식을 지정합니다. 기본 형식은 <xref:System.Array>입니다.

 **사전 컬렉션 형식**

 WCF 클라이언트에 대한 사전 컬렉션 형식을 지정합니다. 기본 형식은 <xref:System.Collections.Generic.Dictionary%602>입니다.

 **참조 된 어셈블리의 형식 재사용**

 WCF 클라이언트 서비스를 추가 하거나 업데이트할 때 새 형식을 생성 하는 대신 참조 된 어셈블리에 이미 무엇을 다시 사용 하려고 시도 하는지 여부를 결정 합니다. 기본적으로 이 옵션은 선택되어 있습니다.

 **모든 참조 된 어셈블리의 형식 재사용**

 선택 하면 모든 형식에는 **참조 된 어셈블리 목록** 가능 하면 다시 사용 됩니다. 기본적으로 이 옵션이 선택됩니다.

 **지정된 된 어셈블리의 형식 재사용**

 선택한 형식만 선택 합니다 **참조 된 어셈블리 목록** 다시 사용 됩니다.

 **참조 된 어셈블리 목록**

 프로젝트 또는 웹 사이트의 참조된 어셈블리 목록을 포함합니다. 선택 하면 **지정된 된 어셈블리의 형식 재사용**를 선택 하거나 개별 어셈블리를 지울 수 있습니다.

 **웹 참조 추가**

 표시 된 **웹 참조 추가** 대화 상자.

> [!NOTE]
> 이 옵션의 2.0 버전을 대상으로 하는 프로젝트에만 사용 해야는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다.

> [!NOTE]
> 합니다 **웹 참조 추가** 단추 때만 사용할 수는 **서비스 참조 구성** 에서 대화 상자가 표시 됩니다는 **서비스 참조 추가 대화 상자**합니다.

## <a name="see-also"></a>참고자료

- [방법: 웹 서비스에 대 한 참조를 추가 합니다.](how-to-add-update-or-remove-a-wcf-data-service-reference.md)
- [Windows Communication Foundation 서비스 및 WCF Data Services](../data-tools/configure-service-reference-dialog-box.md)