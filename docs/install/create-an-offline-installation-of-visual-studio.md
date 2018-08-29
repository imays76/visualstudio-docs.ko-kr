---
title: Visual Studio의 오프라인 설치 만들기
description: Visual Studio를 오프라인으로 설치하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d19eabe10234ca2a1670ae04f99a45a85a6cac14
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138879"
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Visual Studio 2017의 오프라인 설치 만들기

Visual Studio 2017 설치 관리자는 매우 다양한 네트워크 및 컴퓨터 조건에서 제대로 작동하도록 구성되어 있습니다.

- 새 워크로드 기반 모델에서는 Visual Studio의 이전 버전을 포함한 것보다 적게 다운로드해야 합니다(최소 규모 설치의 경우 300MB에 불과함).
- 일반 "ISO" 또는 zip 파일에 비해, 컴퓨터에 필요한 패키지만 다운로드합니다. 예를 들어, 필요하지 않은 경우 64비트 파일을 다운로드하지 않습니다.
- 설치하는 동안 바이러스 백신 및 프록시 소프트웨어의 간섭을 최소화하기 위해 세 가지 다운로드 기술(WebClient, BITS 및 WinInet)이 시도됩니다.
- Visual Studio 설치에 필요한 파일은 전역 배달 네트워크에 배포되므로 로컬 서버에서 해당 파일을 가져올 수 있습니다.

따라서 [Visual Studio 웹 설치 관리자](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)&mdash;를 시도하는 것이 좋습니다. 좋은 경험이 될 것입니다.

 > [!div class="button"]
 > [Visual Studio 2017 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

인터넷 연결을 사용할 수 없거나 인터넷 연결이 불안정하여 오프라인으로 설치하려는 경우 [낮은 대역폭 또는 불안정한 네트워크 환경에 Visual Studio 2017 설치](../install/install-vs-inconsistent-quality-network.md)를 참조하세요. 명령줄을 사용하여 오프라인 설치를 완료하기 필요한 파일의 로컬 캐시를 만들 수 있습니다. 이 프로세스는 이전 버전에 사용 가능한 ISO 파일을 대체합니다.

> [!NOTE]
> 인터넷에서 방화벽이 사용되는 클라이언트 워크스테이션의 네트워크에 대해 Visual Studio 2017의 배포를 수행하려고 하는 엔터프라이즈 관리자인 경우 [Visual Studio 2017의 네트워크 설치 만들기](../install/create-a-network-installation-of-visual-studio.md) 및 [Visual Studio 오프라인 설치에 필요한 인증서 설치](../install/install-certificates-for-visual-studio-offline.md) 페이지를 참조하세요.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]
