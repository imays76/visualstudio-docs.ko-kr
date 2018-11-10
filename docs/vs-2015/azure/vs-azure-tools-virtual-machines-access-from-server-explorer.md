---
title: 서버 탐색기에서 Azure Virtual Machines 액세스 | Microsoft Docs
description: Get 보는 방법에 간략하게 만들기 및 Visual Studio에서 서버 탐색기에서 Azure virtual machines (Vm)를 관리 합니다.
author: ghogen
manager: douge
assetId: eb3afde6-ba90-4308-9ac1-3cc29da4ede0
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/31/2017
ms.author: ghogen
ms.openlocfilehash: e1410b3dc60ec9689b6582e794aaf10cd13092aa
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002353"
---
# <a name="accessing-azure-virtual-machines-from-server-explorer"></a>서버 탐색기에서 Azure Virtual Machines에 액세스

Azure에서 호스팅되는 가상 컴퓨터를 사용 하는 경우에 서버 탐색기에서 액세스할 수 있습니다. 먼저 등록 해야 Azure 구독에 모바일 서비스를 볼 수 있습니다. 로그인 하려면 서버 탐색기에서 Azure 노드에 대 한 바로 가기 메뉴를 열고 선택한 **Microsoft Azure에 연결**합니다.

1. 클라우드 탐색기에서 가상 컴퓨터를 선택 하 고 해당 속성 창을 표시 하려면 F4 키를 선택 합니다.

    다음 표에서 속성을 사용할 수 있지만 모든 읽기 전용입니다. 그것을 변경 하려면 사용 합니다 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040)합니다.

   | 속성 | 설명 |
   | --- | --- |
   | DNS 이름 |가상 컴퓨터의 인터넷 주소 URL입니다. |
   | 환경 |가상 컴퓨터를이 속성의 값은 항상 프로덕션입니다. |
   | 이름 |가상 컴퓨터의 이름입니다. |
   | 크기 |사용 가능한 메모리 및 디스크 공간의 크기를 반영 하는 가상 머신의 크기입니다. 자세한 내용은 [가상 머신 크기](https://docs.microsoft.com/azure/cloud-services/cloud-services-sizes-specs)합니다. |
   | 상태 |값에는 시작, 시작, 중지, 중지 됨 및 상태 검색이 포함 됩니다. 상태 검색이 나타나면 현재 상태를 알려진 아닙니다. 이 속성의 값에 사용 되는 값에서 다를 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040)합니다. |
   | SubscriptionID |Azure 계정에 대 한 구독 ID입니다. 이 정보를 표시할 수 있습니다 합니다 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040) 구독에 대 한 속성을 보고 합니다. |
2. 끝점 노드를 선택한 다음 확인 합니다 **속성** 창입니다.
3. 다음 표에 끝점의 속성을 사용할 수 있지만 읽기 전용입니다. 를 추가 하거나 가상 컴퓨터에 대 한 끝점을 편집 하려면 사용 합니다 [Azure portal](http://go.microsoft.com/fwlink/p/?LinkID=525040)합니다. 

   | 속성 | 설명 |
   | --- | --- |
   | 이름 |끝점에 대 한 식별자입니다. |
   | 개인 포트 |응용 프로그램에 내부 네트워크 액세스 용 포트입니다. |
   | 프로토콜 |사용 하는 프로토콜이이 끝점에 대 한 전송 계층, TCP 또는 UDP입니다. |
   | 공용 포트 |응용 프로그램에 대 한 공용 액세스에 사용 되는 포트입니다. |
