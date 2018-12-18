---
title: Azure 리소스 그룹 프로젝트를 사용 하 여 Azure DevOps 서비스에서 연속 통합 | Microsoft Docs
description: Visual Studio에서 Azure 리소스 그룹 배포 프로젝트를 사용 하 여 Azure DevOps Services에서 연속 통합을 설정 하는 방법에 설명 합니다.
author: mlearned
manager: douge
ms.assetid: b81c172a-be87-4adc-861e-d20b94be9e38
ms.service: azure-resource-manager
ms.topic: article
ms.workload: azure-vs
ms.date: 08/01/2016
ms.author: mlearned
ms.openlocfilehash: b20a43181ad4d36377e61434b880b491543a6c47
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51791607"
---
# <a name="continuous-integration-in-azure-devops-services-using-azure-resource-group-deployment-projects"></a>Azure 리소스 그룹 배포 프로젝트를 사용 하 여 Azure DevOps 서비스에서 연속 통합
Azure 템플릿을 배포 하려면 다양 한 단계에서 작업을 수행 합니다: Azure에 빌드, 테스트, 복사 ("스테이징" 라고도 함) 및 템플릿 배포 합니다. Azure DevOps 서비스에 템플릿을 배포 하려면 두 가지가 있습니다. 두 방법 모두 동일한 결과 제공, 따라서 워크플로 가장 잘 맞는 하나를 선택 합니다.

1. Azure 리소스 그룹 배포 프로젝트 (Deploy-AzureResourceGroup.ps1)에 포함 된 PowerShell 스크립트를 실행 하는 빌드 파이프라인에 단일 단계를 추가 합니다. 스크립트는 아티팩트를 복사 하 고 템플릿을 배포 합니다.
2. 여러 Azure DevOps 서비스 빌드 단계를 수행 단계 작업을 각각 추가 합니다.

이 문서에서는 두 옵션 모두를 보여 줍니다. 첫 번째 옵션을 사용 하면 Visual Studio에서 개발자 및 수명 주기 동안 일관성을 제공 하 여 사용 되는 동일한 스크립트를 사용 하 여 장점이 있습니다. 두 번째 옵션은 기본 제공 스크립트에 편리한 대안을 제공합니다. 두 절차는 이미 Azure DevOps 서비스에 체크 인 Visual Studio 배포 프로젝트를 가정 합니다.

## <a name="copy-artifacts-to-azure"></a>Azure에 아티팩트 복사
시나리오에 관계 없이 템플릿 배포에 필요한 아티팩트가 있을 경우 해야 Azure Resource Manager 액세스 권한을 부여 합니다. 이러한 아티팩트는와 같은 파일을 포함할 수 있습니다.

* 중첩 된 템플릿
* 구성 스크립트 및 DSC 스크립트
* 응용 프로그램 이진 파일

### <a name="nested-templates-and-configuration-scripts"></a>중첩 된 템플릿 및 구성 스크립트
Visual Studio에서 제공 되는 템플릿을 사용 하는 경우 (또는 Visual Studio 스니펫으로 빌드한)도 매개 변수화 하 고 다른 배포에 대 한 리소스에 대 한 URI, PowerShell 스크립트 뿐만 아니라 아티팩트를 준비 합니다. 스크립트를 Azure에서 보안 컨테이너에 아티팩트를 복사, 해당 컨테이너에 대 한 SaS 토큰을 만듭니다 고 템플릿 배포에 해당 정보를 전달 합니다. 참조 [템플릿 배포 만들기](https://msdn.microsoft.com/library/azure/dn790564.aspx) 중첩 된 템플릿에 대 한 자세한 내용은 합니다.  Azure DevOps 서비스에서 작업을 사용 하는 경우 템플릿 배포에 대 한 적절 한 작업을 선택 하 고 필요한 경우 매개 변수 값 전달 준비 단계에서 템플릿 배포 해야 합니다.

## <a name="set-up-continuous-deployment-in-azure-pipelines"></a>Azure 파이프라인에서 연속 배포 설정
Azure 파이프라인에서 PowerShell 스크립트를 호출 하려면 빌드 파이프라인을 업데이트 해야 합니다. 간단히 말해, 단계는 다음과 같습니다. 

1. 빌드 파이프라인을 편집 합니다.
2. Azure 파이프라인에서 Azure 권한 부여를 설정 합니다.
3. Azure 리소스 그룹 배포 프로젝트에서 PowerShell 스크립트를 참조 하는 Azure PowerShell 빌드 단계를 추가 합니다.
4. 값을 설정 합니다 *-ArtifactsStagingDirectory* Azure 파이프라인에서 빌드된 프로젝트를 작성 하려면 매개 변수입니다.

### <a name="detailed-walkthrough-for-option-1"></a>옵션 1에 대 한 자세한 연습
다음 절차에서는 프로젝트에서 PowerShell 스크립트를 실행 하는 단일 작업을 사용 하 여 Azure DevOps 서비스에서 연속 배포를 구성 하는 데 필요한 단계를 안내 합니다. 

1. Azure DevOps 서비스 빌드 파이프라인을 편집 하 고 Azure PowerShell 빌드 단계를 추가 합니다. 빌드 파이프라인을 선택 합니다 **파이프라인을 빌드합니다** 범주를 선택한 후는 **편집** 링크.
   
   ![빌드 파이프라인 편집][0]
2. 새 **Azure PowerShell** 빌드 단계를 빌드 파이프라인으로 선택한 후는 **빌드 단계 추가...** 클릭합니다.
   
   ![빌드 단계 추가][1]
3. 선택 합니다 **배포 작업** 범주를 선택 합니다 **Azure PowerShell** 작업을 선택한 후 해당 **추가** 단추입니다.
   
   ![작업 추가][2]
4. 선택 된 **Azure PowerShell** 빌드 단계 및 해당 값을 입력 합니다.
   
   1. Azure DevOps 서비스에 추가 된 Azure 서비스 끝점이 이미 있는 경우에서 구독을 선택 합니다 **Azure 구독** 드롭다운 목록 상자 및 다음 섹션으로 건너뜁니다. 
      
      Azure DevOps 서비스에서 Azure 서비스 끝점이 없으면 추가 해야 합니다. 이 하위 섹션에서는 과정을 안내합니다. Azure 계정에는 Microsoft 계정 (예: Hotmail)을 사용 하는 경우 서비스 주체 인증을 가져오려면 다음 단계를 수행 해야 합니다.

   2. 선택 된 **관리** 링크 옆에 **Azure 구독** 드롭다운 목록 상자입니다.
      
      ![Azure 구독 관리][3]
   3. 선택할 **Azure** 에 **새 서비스 끝점** 드롭다운 목록 상자입니다.
      
      ![새 서비스 끝점][4]
   4. 에 **Azure 구독 추가** 대화 상자를 선택 합니다 **서비스 주체** 옵션.
      
      ![서비스 주체 옵션][5]
   5. Azure 구독 정보를 추가 합니다 **Azure 구독 추가** 대화 상자. 다음 정보를 제공 해야 합니다.
      
      * 구독 Id
      * 구독 이름
      * 서비스 주체 Id
      * 서비스 주체 키
      * 테 넌 트 Id
   6. 에 선택한 이름을 추가 합니다 **구독** 이름 상자입니다. 이 값의 뒷부분에 **Azure 구독** 드롭다운 목록의 Azure DevOps 서비스입니다. 

   7. Azure 구독 ID를 모르는 경우 검색을 위해 다음 명령 중 하나를 사용할 수 있습니다.
      
      PowerShell 스크립트를 사용 합니다.
      
      `Get-AzureRmSubscription`
      
      Azure CLI를 사용 합니다.
      
      `azure account show`
   8. 서비스 주체 ID, 서비스 주체 키 및 테 넌 트 ID, 다음 절차를 가져오려면 [만드는 Active Directory 응용 프로그램 및 포털을 사용 하 여 서비스 주체](/azure/azure-resource-manager/resource-group-create-service-principal-portal) 또는 [Azure 사용 하 여 서비스 주체 인증 Resource Manager](/azure/azure-resource-manager/resource-group-authenticate-service-principal)합니다.
   9. 서비스 주체 ID, 서비스 주체 키 및 테 넌 트 ID 값을 추가 합니다 **Azure 구독 추가** 대화 상자를 선택한를 **확인** 단추입니다.
      
      이제 유효한 서비스 주체를 사용 하는 Azure PowerShell 스크립트를 실행 해야 합니다.
5. 빌드 파이프라인을 편집 하 고 선택 합니다 **Azure PowerShell** 빌드 단계. 구독을 선택 합니다 **Azure 구독** 드롭다운 목록 상자입니다. (구독이 나타나지 않으면 경우 선택 합니다 **새로 고침** 다음 단추를 **관리** 링크입니다.) 
   
   ![Azure PowerShell 빌드 작업 구성][8]
6. Deploy-AzureResourceGroup.ps1 PowerShell 스크립트에 대 한 경로 제공 합니다. 이렇게 하려면 줄임표 (...) 단추를 옆에 선택 합니다 **스크립트 경로** 상자에서 Deploy-AzureResourceGroup.ps1 PowerShell 스크립트에 **스크립트** 프로젝트의 폴더를 선택한 후 다음 선택 된 **확인** 단추입니다.    
   
   ![스크립트 경로를 선택 합니다.][9]
7. 스크립트를 선택한 후 경로를 업데이트 스크립트를 다음에서 실행할 수 있도록 (동일한 디렉터리는 *ArtifactsLocation* 로 설정 됩니다). "$(Build.StagingDirectory)/ 시작 스크립트 경로입니다"를 추가 하 여이 수행할 수 있습니다.
   
    ![스크립트 경로를 편집 합니다.][10]
8. 에 **스크립트 인수** 상자에 다음 매개 변수 (한 줄)을 입력 합니다. Visual Studio에서 스크립트를 실행 하는 경우 VS에서 매개 변수를 사용 하는 방법을 볼 수 있습니다 합니다 **출력** 창입니다. 빌드 단계에서 매개 변수 값을 설정 하기 위한 시작 점으로 사용할 수 있습니다.
   
   | 매개 변수 | 설명 |
   | --- | --- |
   | -ResourceGroupLocation |리소스 그룹 위치와 같은 지리적 위치 값 **eastus** 하거나 **' East US '** 합니다. (이름에 공백이 없으면 작은따옴표 추가 합니다.) 참조 [Azure 지역](https://azure.microsoft.com/regions/) 자세한 내용은 합니다. |
   | -ResourceGroupName |이 배포에 사용 되는 리소스 그룹의 이름입니다. |
   | -UploadArtifacts |이 매개 변수를 제공 된 경우 지정 하는 로컬 시스템에서 Azure에 업로드 해야 하는 아티팩트입니다. 템플릿 배포 (예: 구성 스크립트 또는 중첩 된 템플릿) PowerShell 스크립트를 사용 하 여 스테이징 하려는 추가 아티팩트가 필요한 경우이 스위치를 설정 해야 합니다. |
   | -StorageAccountName |이 배포에 대 한 스테이지 아티팩트에 사용 된 저장소 계정의 이름입니다. 이 매개 변수는 배포에 대 한 아티팩트를 준비 하는 경우에 사용 됩니다. 이 매개 변수를 제공 하면 스크립트는 이전 배포 중 생성 되지 않은 경우 새 저장소 계정을 생성 됩니다. 매개 변수를 지정 하는 경우 저장소 계정이 이미 있어야 합니다. |
   | -StorageAccountResourceGroupName |저장소 계정에 연결 된 리소스 그룹의 이름입니다. 이 매개 변수는 StorageAccountName 매개 변수에 대 한 값을 제공 하는 경우에 필요 합니다. |
   | -TemplateFile |Azure 리소스 그룹 배포 프로젝트에서 템플릿 파일 경로입니다. 유연성을 강화 하려면 절대 경로 대신 PowerShell 스크립트의 위치를 기준으로 하는이 매개 변수에 대 한 경로 사용 합니다. |
   | -TemplateParametersFile |Azure 리소스 그룹 배포 프로젝트의 매개 변수 파일에 대 한 경로입니다. 유연성을 강화 하려면 절대 경로 대신 PowerShell 스크립트의 위치를 기준으로 하는이 매개 변수에 대 한 경로 사용 합니다. |
   | -ArtifactStagingDirectory |이 매개 변수를 사용 하면 PowerShell을 스크립트에서 프로젝트의 이진 파일을 복사할 폴더를 알고 있습니다. 이 값에는 PowerShell 스크립트에서 사용 되는 기본값을 재정의 합니다. Azure DevOps 서비스 사용에 대 한 값을 설정 합니다.-ArtifactStagingDirectory $ (build.stagingdirectory) |
   
   스크립트 인수 예 (쉽도록 줄 구분)는 다음과 같습니다.
   
   ```    
   -ResourceGroupName 'MyGroup' -ResourceGroupLocation 'eastus' -TemplateFile '..\templates\azuredeploy.json' 
   -TemplateParametersFile '..\templates\azuredeploy.parameters.json' -UploadArtifacts -StorageAccountName 'mystorageacct' 
   –StorageAccountResourceGroupName 'Default-Storage-EastUS' -ArtifactStagingDirectory '$(Build.StagingDirectory)'    
   ```
   
   를 완료 합니다 **스크립트 인수** 상자가 다음과 유사 합니다.:
   
   ![스크립트 인수][11]
9. Azure PowerShell 빌드 단계에 필요한 모든 항목을 추가한 후 선택 합니다 **큐** 빌드 프로젝트를 작성 하려면 단추입니다. 합니다 **빌드** 화면에는 PowerShell 스크립트에서 출력을 보여 줍니다.

### <a name="detailed-walkthrough-for-option-2"></a>옵션 2에 대 한 자세한 연습
다음 절차에서는 기본 제공 작업을 사용 하 여 Azure DevOps 서비스에서 연속 배포를 구성 하는 데 필요한 단계를 안내 합니다.

1. 두 가지 새로운 빌드 단계를 추가 하려면 Azure DevOps 서비스 빌드 파이프라인을 편집 합니다. 아래에서 빌드 파이프라인을 선택 합니다 **빌드 정의** 범주를 선택한 후는 **편집** 링크.
   
   ![빌드 정의 편집][12]
2. 새 빌드 단계를 사용 하 여 빌드 파이프라인에 추가 된 **빌드 단계 추가...** 클릭합니다.
   
   ![빌드 단계 추가][13]
3. 선택 합니다 **배포** 작업 범주를 선택 합니다 **Azure 파일 복사** 작업을 선택한 후 해당 **추가** 단추입니다.
   
   ![Azure File Copy 작업 추가][14]
4. 선택 된 **Azure 리소스 그룹 배포** 선택한 작업을 해당 **추가** 단추 차례로 **닫기** 는 **작업 카탈로그**합니다.
   
   ![Azure 리소스 그룹 배포 작업 추가][15]
5. 선택 된 **Azure File Copy** 작업 및 해당 값을 입력 합니다.
   
   Azure DevOps 서비스에 추가 된 Azure 서비스 끝점이 이미 있는 경우에서 구독을 선택 합니다 **Azure 구독** 드롭다운 목록 상자입니다. 구독이 없으면 참조 [옵션 1](#detailed-walkthrough-for-option-1) Azure DevOps 서비스에서 설정에 대 한 지침에 대 한 합니다.
   
   * 원본-입력 **$ (build.stagingdirectory)**
   * Azure 연결 형식-선택 **Azure Resource Manager**
   * Azure RM 구독-에서 사용 하려는 저장소 계정에 대 한 구독을 선택 합니다 **Azure 구독** 드롭다운 목록 상자입니다. 구독이 나타나지 않으면 경우 선택 합니다 **새로 고침** 다음 단추를 **관리** 링크 합니다.
   * 대상 유형-선택 **Azure Blob**
   * RM 저장소 계정-선택 된 저장소 계정을 아티팩트 준비에 사용 하려고 합니다.
   * 컨테이너 이름-준비;에 사용 하려는 컨테이너의 이름을 입력 합니다. 모든 유효한 컨테이너 이름이 될 수 있지만이 빌드 파이프라인 하나를 사용 하 여
   
   출력 값:
   
   * 저장소 컨테이너 URI-입력 **artifactsLocation**
   * 저장소 컨테이너 SAS 토큰-입력 **artifactsLocationSasToken**
   
   ![Azure File Copy 작업 구성][16]
6. 선택 된 **Azure 리소스 그룹 배포** 빌드 단계 및 해당 값을 입력 합니다.
   
   * Azure 연결 형식-선택 **Azure Resource Manager**
   * Azure RM 구독-에서 배포에 대 한 구독을 선택 합니다 **Azure 구독** 드롭다운 목록 상자입니다. 이전 단계에서 사용한 동일한 구독 보통은이
   * 작업- **만들기 또는 리소스 그룹 업데이트**
   * 리소스 그룹-리소스 그룹을 선택 하거나 배포에 대 한 새 리소스 그룹의 이름을 입력 합니다.
   * 위치-리소스 그룹의 위치를 선택 합니다.
   * 템플릿-배포 될 템플릿의 이름과 경로 입력 합니다. 앞 **$ (build.stagingdirectory)** 예를 들어: **$(Build.StagingDirectory/DSC-CI/azuredeploy.json)**
   * 템플릿 매개 변수 입력 경로 및 사용할 매개 변수 이름 앞 **$ (build.stagingdirectory)** 예를 들어: **$(Build.StagingDirectory/DSC-CI/azuredeploy.parameters.json)**
   * 템플릿 매개 변수 재정의-입력 또는 복사한 다음 코드를 붙여 넣습니다.
     
     ```    
     -_artifactsLocation $(artifactsLocation) -_artifactsLocationSasToken (ConvertTo-SecureString -String "$(artifactsLocationSasToken)" -AsPlainText -Force)
     ```
     ![Azure 리소스 그룹 배포 작업 구성][17]
7. 모든 필요한 항목을 추가한 후 빌드 파이프라인을 저장 하 고 선택 **새 빌드 큐 대기** 맨 위에 있는 합니다.

## <a name="next-steps"></a>다음 단계
읽기 [Azure Resource Manager 개요](/azure-resource-manager/resource-group-overview.md) Azure Resource Manager 및 Azure 리소스 그룹에 자세히 알아보려면 합니다.

[0]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough1.png
[1]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough2.png
[2]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough3.png
[3]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough4.png
[4]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough5.png
[5]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough6.png
[8]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough9.png
[9]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough10.png
[10]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough11b.png
[11]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough12.png
[12]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough13.png
[13]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough14.png
[14]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough15.png
[15]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough16.png
[16]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough17.png
[17]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough18.png
