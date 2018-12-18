---
title: Publish-webapplicationvm | Microsoft Docs
description: 가상 머신에 웹 응용 프로그램을 배포 하는 방법에 알아봅니다. 이 스크립트는 없는 경우 Azure 구독에 필요한 리소스를 만듭니다.
author: ghogen
manager: douge
assetId: de4cec95-f73f-44d9-babd-9f47f2633cdb
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: c2383e6d7b14d801a391a725f0482736fb926cd1
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51003003"
---
# <a name="publish-webapplicationvm-windows-powershell-script"></a>Publish-WebApplicationVM(Windows PowerShell 스크립트)
가상 머신에 웹 응용 프로그램을 배포합니다. 스크립트가 없는 경우 Azure 구독에 필요한 리소스를 만듭니다.

```
Publish-WebApplicationVM
–Configuration <configuration>
-SubscriptionName <subscriptionName>
-WebDeployPackage <packageName>
-VMPassword @{Name = "name"; Password = "password")
-DatabaseServerPassword @{Name = "name"; Password = "password"}
-SendHostMessagesToOutput
-Verbose
```

### <a name="configuration"></a>구성
배포의 세부 정보를 설명 하는 JSON 구성 파일에 대 한 경로입니다.

| 별칭 | 없음 |
| --- | --- |
| 필수 여부 |true |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

### <a name="subscriptionname"></a>SubscriptionName
가상 컴퓨터를 만들려는 Azure 구독의 이름입니다.

| 별칭 | 없음 |
| --- | --- |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |구독 파일에서 첫 번째 구독을 사용 하 여 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

### <a name="webdeploypackage"></a>WebDeployPackage
가상 컴퓨터에 게시 하려면 웹 배포 패키지에 대 한 경로입니다. Visual Studio에서 웹 게시 마법사를 사용 하 여이 패키지를 만들 수 있습니다. 참조 [방법: Visual Studio에서 웹 배포 패키지 만들기](https://msdn.microsoft.com/library/dd465323.aspx)합니다.

| 별칭 | 없음 |
| --- | --- |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

### <a name="allowuntrusted"></a>AllowUntrusted
True 인 경우 신뢰할 수 있는 루트 기관에서 서명 되지 않은 인증서 사용을 허용 합니다.

| 별칭 | 없음 |
| --- | --- |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |False |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

### <a name="vmpassword"></a>VMPassword
가상 컴퓨터 계정의 자격 증명입니다. 예:-VMPassword @{Name = "admin"; 암호 = "password"}

| 별칭 | 없음 |
| --- | --- |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

### <a name="databaseserverpassword"></a>DatabaseServerPassword
Azure에서 SQL database에 대 한 자격 증명입니다. 예:-DatabaseServerPassword @{Name = "admin"; 암호 = "password"}

| 별칭 | 없음 |
| --- | --- |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |없음 |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

### <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
True 이면 출력 스트림에 인쇄 스크립트에서 메시지입니다.

| 별칭 | 없음 |
| --- | --- |
| 필수 여부 |False |
| 위치 |명명됨 |
| 기본값 |False |
| 파이프라인 입력 허용 |False |
| 와일드 카드 문자를 허용 하 시겠습니까? |False |

## <a name="remarks"></a>설명
개발 및 테스트 환경 참조 만들기 스크립트를 사용 하는 방법에 대 한 전체 설명은 [개발 및 테스트 환경에 게시 하려면 Windows PowerShell 스크립트를 사용 하 여](vs-azure-tools-publishing-using-powershell-scripts.md)입니다.

JSON 구성 파일을 배포 하는 항목의 세부 정보를 지정 합니다. 이름, 선호도 그룹, VHD 이미지 및 가상 컴퓨터의 크기와 같은 프로젝트를 만들 때 지정한 정보를 포함 합니다. 또한 있으면 가상 컴퓨터를 프로 비전 하려면 데이터베이스에서 끝점을 포함 하 고 웹 배포 매개 변수입니다. 다음 코드 예제에서는 JSON 구성 파일을 보여 줍니다.

```
{
    "environmentSettings": {
        "cloudService": {
            "name": "myvmname",
            "affinityGroup": "",
            "location": "West US",
            "virtualNetwork": "",
            "subnet": "",
            "availabilitySet": "",
            "virtualMachine": {
                "name": "myvmname",
                "vhdImage": "a699494373c04fc0bc8f2bb1389d6106__Windows-Server-2012-R2-201404.01-en.us-127GB.vhd",
                "size": "Small",
                "user": "vmuser1",
                "password": "",
                "enableWebDeployExtension": true,
                "endpoints": [
                    {
                        "name": "Http",
                        "protocol": "TCP",
                        "publicPort": "80",
                        "privatePort": "80"
                    },
                    {
                        "name": "Https",
                        "protocol": "TCP",
                        "publicPort": "443",
                        "privatePort": "443"
                    },
                    {
                        "name": "WebDeploy",
                        "protocol": "TCP",
                        "publicPort": "8172",
                        "privatePort": "8172"
                    },
                    {
                        "name": "Remote Desktop",
                        "protocol": "TCP",
                        "publicPort": "3389",
                        "privatePort": "3389"
                    },
                    {
                        "name": "Powershell",
                        "protocol": "TCP",
                        "publicPort": "5986",
                        "privatePort": "5986"
                    }
                ]
            }
        },
        "databases": [
            {
                "connectionStringName": "",
                "databaseName": "",
                "serverName": "",
                "user": "",
                "password": ""
            }
        ],
        "webDeployParameters": {
            "iisWebApplicationName": "Default Web Site"
        }
    }
}
```

프로 비전 한 내용을 변경 하도록 JSON 구성 파일을 편집할 수 있습니다. 가상 머신 및 클라우드 서비스는 필요 하지만 데이터베이스 섹션은 선택 사항입니다.

