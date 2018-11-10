---
title: Publish-webapplicationwebsite (Windows PowerShell 스크립트) | Microsoft Docs
description: Azure 웹 사이트에 웹 프로젝트를 게시 하는 방법에 알아봅니다. 이 스크립트는 없는 경우 Azure 구독에 필요한 리소스를 만듭니다.
author: ghogen
manager: douge
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: 175181d5d866e9d7fab51eaf7c3262e47d0ed6a8
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002893"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite(Windows PowerShell 스크립트)
## <a name="syntax"></a>구문
Azure 웹 사이트를 웹 프로젝트를 게시합니다. 스크립트가 없는 경우 Azure 구독에 필요한 리소스를 만듭니다.

    Publish-WebApplicationWebSite
    –Configuration <configuration>
    -SubscriptionName <subscriptionName>
    -WebDeployPackage <packageName>
    -DatabaseServerPassword @{Name = "name"; Password = "password"}
    -SendHostMessagesToOutput
    -Verbose


## <a name="configuration"></a>구성
배포의 세부 정보를 설명 하는 JSON 구성 파일에 대 한 경로입니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |true |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

## <a name="subscriptionname"></a>SubscriptionName
웹 사이트를 만들려는 Azure 구독의 이름입니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

## <a name="webdeploypackage"></a>WebDeployPackage
웹 사이트에 게시 하려면 웹 배포 패키지에 대 한 경로입니다. Visual Studio에서 웹 게시 마법사를 사용 하 여이 패키지를 만들 수 있습니다. 자세한 내용은 [Azure Cloud Services 및 ASP.NET 시작](http://go.microsoft.com/fwlink/p/?LinkID=623089)합니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

## <a name="databaseserverpassword"></a>DatabaseServerPassword
사용자 이름 및 azure에서 SQL database에 대 한 암호입니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

## <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
True 이면 출력 스트림에 인쇄 스크립트에서 메시지입니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |False |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

## <a name="remarks"></a>설명
개발 및 테스트 환경 참조 만들기 스크립트를 사용 하는 방법에 대 한 전체 설명은 [개발 및 테스트 환경에 게시 하려면 Windows PowerShell 스크립트를 사용 하 여](vs-azure-tools-publishing-using-powershell-scripts.md)입니다.

JSON 구성 파일을 배포 하는 항목의 세부 정보를 지정 합니다. 웹 사이트에 대 한 이름과 같은 프로젝트를 만들 때 지정한 정보를 포함 합니다. 도 있는 경우 데이터베이스를 프로 비전을 포함 합니다. 다음 코드 예제에서는 JSON 구성 파일을 보여 줍니다.

    {
        "environmentSettings": {
            "webSite": {
                "name": "WebApplication10554",
                "location": "West US"
            },
            "databases": [
                {
                    "connectionStringName": "DefaultConnection",
                    "databaseName": "WebApplication10554_db",
                    "serverName": "iss00brc88",
                    "user": "sqluser2",
                    "password": "",
                    "edition": "",
                    "size": "",
                    "collation": "",
                    "location": "West US"
                }
            ]
        }
    }

배포 된 내용을 변경 하도록 JSON 구성 파일을 편집할 수 있습니다. 웹 사이트 섹션은 필수 이지만 데이터베이스 섹션은 선택 사항입니다.

## <a name="next-steps"></a>다음 단계
자세한 내용은 참조 하세요. [Publish-webapplicationvm (Windows PowerShell 스크립트)](vs-azure-tools-publish-webapplicationvm.md)

