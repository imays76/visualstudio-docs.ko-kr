---
title: Visual Studio로 사설 Azure 클라우드에 액세스 | Microsoft Docs
description: Visual Studio를 사용 하 여 사설 클라우드 리소스에 액세스 하는 방법을 알아봅니다.
author: ghogen
manager: douge
assetId: 9d733c8d-703b-44e7-a210-bb75874c45c8
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/13/2017
ms.author: ghogen
ms.openlocfilehash: 216b85e0ebf42b79c388ce217d548f2dce3c86b6
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002963"
---
# <a name="accessing-private-azure-clouds-with-visual-studio"></a>Visual Studio로 사설 Azure 클라우드에 액세스

기본적으로 Visual Studio는 Azure 클라우드 REST 끝점을 지원합니다. 이 문서에서는 사설 클라우드의 인증서를 사용 하 여 액세스 하 고 Visual Studio에서 사설 클라우드를 사용 하 여 상호 작용 하는 방법을 알아봅니다.

1. 사설 클라우드 용 Azure 포털의 게시 설정 파일을 다운로드 하거나 게시 설정 파일에 대 한 관리자에 게 문의 합니다. (파일 확장명이 `.publishsettings`.)

1. Visual Studio에서 **서버 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **Azure** 노드와 선택 **구독 관리 및 필터링**합니다.

    ![구독 명령 관리](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790778.png)

1. 에 **Microsoft Azure 구독 관리** 대화 상자에서 선택 합니다 **인증서** 탭을 선택한 다음 선택 **가져오기**합니다.

    ![Azure 인증서 가져오기](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790779.png)

1. 에 **Microsoft Azure 구독 가져오기** 대화 상자에서 **찾아보기**합니다.

    ![Microsoft Azure 구독 가져오기 대화 상자에서 단추 찾아보기](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/browse-button.png)

1. 에 **엽니다** 대화 상자에서 게시 설정 파일을 저장 한 디렉터리로 이동 선택 하 고 파일을 선택 **열기**합니다.

    ![게시 설정 파일 선택](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/select-publish-settings-file.png)

1. 반환 하는 경우는 **Microsoft Azure 구독 가져오기** 대화 상자에서 **가져오기**합니다.

    ![게시 설정 파일 가져오기](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790780.png)

    Visual Studio로 게시 설정 파일에서 가져온 인증서 및 사설 클라우드 리소스를 이제 조작할 수 있습니다.

