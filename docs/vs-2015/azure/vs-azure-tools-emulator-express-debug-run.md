---
title: Emulator Express를 사용 하 여 실행 하 고 로컬 컴퓨터에서 Azure 클라우드 서비스 디버그 | Microsoft Docs
description: Emulator Express를 사용 하 여 실행 하 고 로컬 컴퓨터에서 클라우드 서비스 디버깅
author: mikejo5000
manager: douge
ms.assetid: 73108f98-a552-4817-b7a1-551367b71906
ms.topic: conceptual
ms.workload: azure-vs
ms.date: 03/06/2017
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 28dd59e3d691df0199afffe93d68d60668c6afe4
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002343"
---
# <a name="using-emulator-express-to-run-and-debug-an-azure-cloud-service-on-a-local-machine"></a>Emulator Express를 사용하여 로컬 머신에서 Azure 클라우드 서비스 실행 및 디버그
Emulator Express를 사용 하 여 테스트 하 고 관리자 권한으로 Visual Studio를 실행 하지 않고 클라우드 서비스를 디버그할 수 있습니다. 프로젝트 설정을 Emulator Express 또는 클라우드 서비스의 요구 사항에 따라 전체 에뮬레이터를 사용 하도록 설정할 수 있습니다. 전체 에뮬레이터에 대 한 자세한 내용은 참조 하세요. [Compute 에뮬레이터에서 Azure 응용 프로그램을 실행](/azure/storage/common/storage-use-emulator)합니다.

## <a name="using-emulator-express-in-visual-studio"></a>Visual Studio에서 Emulator Express 사용
Azure SDK 2.3 이상에서 Azure 프로젝트를 만들 때 Emulator Express 사용 자동으로 됩니다. 이전 버전의 Azure SDK를 사용 하 여 만들어진 기존 프로젝트의 경우 Emulator Express를 선택 하려면 다음 단계를 사용 합니다.

1. 만들거나 Visual Studio에서 Azure 클라우드 서비스 프로젝트를 엽니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭, 상황에 맞는 메뉴에서 선택 **속성**합니다.

1. 프로젝트 속성 페이지에서 선택 합니다 **웹** 탭 합니다.

    ![Azure 클라우드 서비스 프로젝트에 대 한 속성](./media/vs-azure-tools-emulator-express-debug-run/web-properties.png)

1. 아래 **로컬 개발 서버**를 선택 **IIS Express 사용 옵션**합니다.

1. 아래 **에뮬레이터**를 선택 **Emulator Express 사용**합니다.
   
1. Emulator Express를 시작 하려면 명령 프롬프트에서 다음 명령을 실행 합니다. 

    ```
    csrun.exe /useemulatorexpress
    ```

## <a name="emulator-express-limitations"></a>Emulator Express 제한 사항
다음 문제는 Emulator Express의 제한 사항 알려져 있습니다. 

- Emulator Express는 IIS 웹 서버와 호환 되지 않습니다.
- 클라우드 서비스에는 여러 역할을 포함할 수 있지만 각 역할은 하나의 인스턴스로 제한 됩니다.
- 1000 아래의 포트 번호를 액세스할 수 없습니다. 일반적으로 1000 아래의 포트를 사용 하는 인증 공급자를 사용 하는 경우 1000 위의 포트 번호로이 값을 변경 해야 합니다.
- Azure Compute 에뮬레이터에 적용 되는 한 제한 사항은 Emulator Express에 적용 됩니다. 예를 들어 배포당 50 개 이상의 역할 인스턴스를 사용할 수 없습니다. Azure Compute 에뮬레이터에 대 한 자세한 내용은 참조 하세요. [Compute 에뮬레이터에서 Azure 응용 프로그램을 실행](http://go.microsoft.com/fwlink/p/?LinkId=623050)합니다.

## <a name="next-steps"></a>다음 단계
[Azure cloud services 디버깅](https://msdn.microsoft.com/library/azure/ee405479.aspx)
