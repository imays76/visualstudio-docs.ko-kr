---
title: Cloud services 디버깅 Azure 옵션 | Microsoft Docs
description: Azure cloud services 디버깅
author: mikejo5000
manager: douge
ms.assetid: 80755da7-8350-4f5c-97ce-2962beabb36d
ms.topic: conceptual
ms.workload: azure-vs
ms.date: 03/18/2017
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.openlocfilehash: bd2608371871b7adc925fc11927fe061b00a1ec6
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002883"
---
# <a name="learn-the-various-ways-to-debug-an-azure-cloud-service"></a>Azure 클라우드 서비스를 디버그하는 다양한 방법 알아보기
이 문서에서는 Azure 클라우드 서비스를 디버그 하는 다양 한 방법에 대 한 링크를 제공 합니다. 

## <a name="debugging-an-azure-cloud-service-in-visual-studio"></a>Visual Studio에서 Azure 클라우드 서비스 디버깅
시간을 절약할 수 및 Azure를 사용 하 여 비용 계산 에뮬레이터는 로컬 컴퓨터에서 클라우드 서비스를 디버그 합니다. 배포 하기 전에 로컬로 서비스를 디버깅, 계산 시간에 대 한 비용을 지불 하지 않고 안정성과 성능을 향상 시킬 수 있습니다. 그러나 일부 오류는 Azure에서 클라우드 서비스를 실행 하는 경우에 발생할 수 있습니다. 서비스에 게시할 때 원격 디버깅 및 다음 역할 인스턴스에 디버거를 연결 함으로써 Azure에서 클라우드 서비스를 실행 하는 경우에 발생 하는 오류를 디버그할 수 있습니다. 자세한 내용은 [로컬 컴퓨터에서 클라우드 서비스 디버그](vs-azure-tools-debug-cloud-services-virtual-machines.md#debug-your-cloud-service-on-your-local-computer)합니다.

## <a name="using-intellitrace"></a>IntelliTrace 사용 
Visual Studio Enterprise를 사용 하 여.NET Framework 4.5를 대상으로 역할을 작성 하는, 경우에 Visual Studio에서 Azure 클라우드 서비스를 배포 하는 시점에 IntelliTrace를 사용할 수 있습니다. IntelliTrace는 Azure에서 실행 되는 것 처럼 응용 프로그램을 디버깅 하려면 Visual Studio를 사용 하 여 사용할 수 있는 로그를 제공 합니다. 자세한 내용은 [IntelliTrace 및 Visual Studio를 사용 하 여 게시 된 클라우드 서비스 디버깅](http://go.microsoft.com/fwlink/p/?LinkId=623016)합니다.

## <a name="remote-debugging"></a>원격 디버깅 
Visual Studio에서 클라우드 서비스를 배포 하는 경우 시간에 클라우드 서비스에서 원격 디버깅을 사용할 수 있습니다. 배포에 대 한 원격 디버깅을 사용 하려는 경우 원격 디버깅 서비스는 각 역할 인스턴스를 실행 하는 가상 컴퓨터에 설치 됩니다. 와 같은 서비스 `msvsmon.exe` -하지 성능에 영향을 않거나 추가 비용이 발생 합니다. 자세한 내용은 [Azure에서 클라우드 서비스 디버그](vs-azure-tools-debug-cloud-services-virtual-machines.md#debug-a-cloud-service-in-azure)합니다.

## <a name="next-steps"></a>다음 단계
- [Azure 클라우드 서비스 또는 VM Visual Studio에서 디버깅](./vs-azure-tools-debug-cloud-services-virtual-machines.md) -Azure cloud services를 디버깅 하는 방법 자세히 알아봅니다.