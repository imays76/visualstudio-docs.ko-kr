---
title: 명명 된 인증 자격 증명 설정 | Microsoft Docs
description: Visual Studio는 Visual Studio에서 Azure로 응용 프로그램을 게시 하거나 기존 클라우드 서비스를 모니터링할 수 있도록 Azure에 대 한 요청을 인증 하는 데 사용할 수 있는 자격 증명을 제공 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: 61570907-42a1-40e8-bcd6-952b21a55786
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2017
ms.author: ghogen
ms.openlocfilehash: 6f41ea2072ef5791735fac61205f68151d5a9f7e
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002913"
---
# <a name="set-up-named-authentication-credentials"></a>명명된 인증 자격 증명 설정

Azure에 응용 프로그램을 게시 하거나 기존 클라우드 서비스를 모니터링 하려면 Visual Studio 즉: Azure 구독 ID 및 2,048 비트 이상의 키를 사용 하 여 유효한 X.509 v3 인증서를 azure에 요청을 인증 하려면 자격 증명이 필요 합니다. 다음 방법 중 하나를 통해 이러한 자격 증명을 제공 합니다.

- Visual Studio에서 **보기 > 서버 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **Azure** 노드를 선택 **Microsoft Azure 구독에 연결**, 로그인 합니다.
- 구독 파일을 만듭니다 (`.publishsettings`), 인증서의 공개 키를 포함 하는 합니다. 이 문서에 설명 된 대로 구독 파일에는 둘 이상의 구독에 대 한 자격 증명을 포함할 수 있습니다.

참고: 이러한 자격 증명은 Azure storage 서비스에 요청을 인증 하는 데 사용 되는 자격 증명과 다릅니다.

## <a name="create-a-subscription-file"></a>구독 파일 만들기

서버 탐색기에서 마우스 오른쪽 단추로 클릭 합니다 **Azure** 노드와 선택 **구독 관리 및 필터링**합니다. 다음을 선택 합니다 **인증서** 탭을 선택한 후 다음 작업 중 하나를 수행 합니다.

- 선택 **가져오기** 열려는 합니다 **Microsoft Azure 구독 가져오기** 대화 상자. 선택 된 **구독 파일 다운로드** 링크를 선택한 브라우저에서 다운로드 한 파일을 임시 위치에 저장 합니다. 대화 상자에서 다시 다운로드 위치로 이동 하 고 인증에 사용할 수 있게 가져옵니다.
- 활성 구독을 선택 하 고 선택 **편집**, 인증에 사용할 기존 구독을 편집할 수 있는 대화 상자가 열립니다.
- 선택 **새로 만들기** 열려는 합니다 **새 구독** 대화 상자 및 필요한 세부 정보를 제공 합니다. 클라우드에 인증서를 업로드 하려면 서비스 대화 상자에서 나와 Azure portal에 로그인, 클라우드 서비스 선택으로 이동 **설정 > 관리 인증서**를 선택 **업로드**, 한 다음 경로를 지정 합니다 `.cer` 파일입니다.

인증서를 직접 만들려면의 지침을 참조할 수 있습니다 [Azure 용 관리 인증서 만들기 및 업로드](https://msdn.microsoft.com/library/windowsazure/gg551722.aspx) 한 다음 인증서를 수동으로 업로드를 [Azure portal](https://portal.azure.com/)합니다.

## <a name="next-steps"></a>다음 단계

- [웹 앱의 일반적인 개요](https://docs.microsoft.com/azure/app-service/)
- [Azure App Service에 앱 배포](https://docs.microsoft.com/azure/app-service/app-service-deploy-local-git) 
- [Visual Studio를 사용 하 여 WebJobs를 배포 합니다.](https://docs.microsoft.com/azure/app-service/websites-dotnet-deploy-webjobs)
- [클라우드 서비스 만들기 및 배포](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy-portal)