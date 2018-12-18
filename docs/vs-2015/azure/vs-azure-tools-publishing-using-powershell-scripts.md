---
title: Windows PowerShell 스크립트를 사용 하 여 개발 및 테스트 환경에 게시할 | Microsoft Docs
description: Visual Studio에서 Windows PowerShell 스크립트를 개발에 게시 하 여 테스트 환경을 사용 하는 방법에 알아봅니다.
author: ghogen
manager: douge
assetId: 5fff1301-5469-4d97-be88-c85c30f837c1
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: 9d0142c52fbe40256fc0ab6ec0d5d9fdade243b7
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002718"
---
# <a name="using-windows-powershell-scripts-to-publish-to-dev-and-test-environments"></a>Windows PowerShell 스크립트를 사용하여 개발 및 테스트 환경에 게시

Visual Studio에서 웹 응용 프로그램을 만들 때 Azure App Service 또는 가상 컴퓨터에서 웹 앱으로 Azure에 웹 사이트의 게시를 자동화 하려면 나중에 사용할 수 있는 Windows PowerShell 스크립트를 생성할 수 있습니다. 편집 하 여 요구 사항에 맞게 Visual Studio 편집기에서 Windows PowerShell 스크립트를 확장 하거나 기존 빌드, 테스트 및 게시 스크립트를 사용 하 여 스크립트에 통합할 수 있습니다.

이러한 스크립트를 사용 하 여 일시적으로 사용할 사이트의 사용자 지정 된 버전 (라고도: 개발 및 테스트 환경)를 제공할 수 있습니다. 예를 들어, Azure 가상 머신에서 또는 테스트 제품군 실행, 버그를 재현, 버그 수정, 평가판 제안된 된 변경 테스트 또는 데모 또는 프레젠테이션을 위한 사용자 지정 환경을 설정 하 여 웹 사이트에 스테이징 슬롯에서 웹 사이트의 특정 버전을 설정할 수 있습니다. 프로젝트를 게시 하는 스크립트를 만든 후에 필요에 따라 스크립트를 다시 실행 하 여 동일한 환경을 다시 수도 있고 테스트에 대 한 사용자 지정 환경을 만들려면 웹 응용 프로그램의 자체 빌드로 스크립트를 실행 수 있습니다.

## <a name="prerequisites"></a>전제 조건

* Azure SDK 2.3 이상입니다. 참조 [Visual Studio 다운로드](http://go.microsoft.com/fwlink/?LinkID=624384)합니다. (웹 프로젝트용 스크립트를 생성 하기 위해 Azure SDK를 필요 하지 않습니다. 이 기능은 클라우드 서비스의 웹 역할이 아닌 웹 프로젝트용입니다.)
* Azure PowerShell 0.7.4 이상. 참조 [Azure PowerShell 설치 및 구성 하는 방법을](/powershell/azure/overview)합니다.
* [Windows PowerShell 3.0](http://go.microsoft.com/?linkid=9811175) 이상.

## <a name="additional-tools"></a>추가 도구

Azure 개발을 위한 Visual Studio에서 PowerShell을 사용 하기 위한 추가 도구 및 리소스 사용할 수 있습니다. 참조 [Visual Studio 용 PowerShell 도구](http://go.microsoft.com/fwlink/?LinkId=404012)합니다.

## <a name="generating-the-publish-scripts"></a>게시 스크립트 생성

수행 하 여 새 프로젝트를 만들면 웹 사이트를 호스팅하는 가상 컴퓨터에 대 한 게시 스크립트를 생성할 수 있습니다 [이러한 지침](/azure/virtual-machines/windows/classic/web-app-visual-studio.md?toc=%2fazure%2fvirtual-machines%2fwindows%2fclassic%2ftoc.json)합니다. 할 수도 있습니다 [생성 Azure App Service에서 웹 앱에 대 한 스크립트를 게시](/azure/app-service/scripts/app-service-powershell-deploy-github)합니다.

## <a name="scripts-that-visual-studio-generates"></a>Visual Studio에서 생성 하는 스크립트

Visual Studio에서 호출 하는 솔루션 수준의 폴더 생성 **PublishScripts** 두 개의 Windows PowerShell 파일을 가상 컴퓨터 또는 웹 사이트에서 사용할 수 있는 함수가 포함 된 모듈에 대 한 게시 스크립트를 포함 하는 스크립트입니다. 또한 visual Studio를 배포 하는 프로젝트의 세부 정보를 지정 하는 JSON 형식으로 파일을 생성 합니다.

### <a name="windows-powershell-publish-script"></a>Windows PowerShell 게시 스크립트

게시 스크립트에는 웹 사이트 또는 가상 컴퓨터를 배포 하기 위한 특정 게시 단계가 포함 되어 있습니다. Visual Studio는 Windows PowerShell 개발을 위한 구문 색 지정을 제공 합니다. 도움말을 함수를 사용할 수 있고 변경 요구 사항에 맞게 스크립트의 함수를 자유롭게 편집할 수 있습니다.

### <a name="windows-powershell-module"></a>Windows PowerShell 모듈

Visual Studio에서 생성 하는 Windows PowerShell 모듈에는 게시 스크립트를 사용 하는 함수가 포함 됩니다. 이러한 Azure PowerShell 함수는 수정할 수 없습니다. 참조 [Azure PowerShell 설치 및 구성 하는 방법을](/powershell/azure/overview)합니다.

### <a name="json-configuration-file"></a>JSON 구성 파일

JSON 파일이 만들어집니다는 **구성을** 폴더 정확 하 게 Azure에 배포 하는 리소스를 지정 하는 구성 데이터를 포함 합니다. Visual Studio에서 생성 된 파일의 이름은 프로젝트-이름-WAWS-dev.json 가상 머신을 만든 경우 웹 사이트 또는 프로젝트 이름-VM-dev.json를 생성 하는 경우. 웹 사이트를 만들 때 생성 되는 JSON 구성 파일의 예는 다음과 같습니다. 대부분의 값은 설명이 따로 필요 없습니다. 하므로 프로젝트 이름과 일치 하지 않을 수 있습니다 웹 사이트 이름은 Azure에서 생성 됩니다.

```json
{
    "environmentSettings": {
        "webSite": {
            "name": "WebApplication26632",
            "location": "West US"
        },
        "databases": [{
            "connectionStringName": "DefaultConnection",
            "databaseName": "WebApplication26632_db",
            "serverName": "YourDatabaseServerName",
            "user": "sqluser2",
            "password": "",
            "edition": "",
            "size": "",
            "collation": "",
            "location": "West US"
        }]
    }
}
```

가상 컴퓨터를 만들면 JSON 구성 파일에는 다음과 유사 합니다. 클라우드 서비스는 가상 머신의 컨테이너로 생성 됩니다. 가상 머신에 HTTP 및 HTTPS를 통한 웹 액세스용 일반 끝점과 뿐만 아니라 로컬 컴퓨터, 원격 데스크톱 및 Windows PowerShell에서 웹 사이트에 게시할 수 있는 웹 배포에 대 한 끝점을 포함 합니다.

```json
{
    "environmentSettings": {
        "cloudService": {
            "name": "myusernamevm1",
            "affinityGroup": "",
            "location": "West US",
            "virtualNetwork": "",
            "subnet": "",
            "availabilitySet": "",
            "virtualMachine": {
                "name": "myusernamevm1",
                "vhdImage": "a699494373c04fc0bc8f2bb1389d6106__Win2K8R2SP1-Datacenter-201403.01-en.us-127GB.vhd",
                "size": "Small",
                "user": "vmuser1",
                "password": "",
                "enableWebDeployExtension": true,
                "endpoints": [{
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
        "databases": [{
            "connectionStringName": "",
            "databaseName": "",
            "serverName": "",
            "user": "",
            "password": ""
        }],
        "webDeployParameters": {
            "iisWebApplicationName": "Default Web Site"
        }
    }
}
```

게시 스크립트를 실행할 때 발생 하는 항목을 변경 하려면 JSON 구성을 편집할 수 있습니다. `cloudService` 하 고 `virtualMachine` 섹션에는 필요 하지만 삭제할 수 있습니다는 `databases` 필요가 없는 경우 섹션. Visual Studio에서 생성 하는 기본 구성 파일에서 비어 있는 속성은 선택 사항입니다. 기본 구성 파일에서 값이 있는 해당 속성은 필수입니다.

Azure에서 단일 프로덕션 사이트가 아닌 여러 배포 환경 (슬롯 이라고 함)이 있는 웹 사이트에 있는 경우에 JSON 구성 파일에서 웹 사이트 이름에 슬롯 이름을 포함할 수 있습니다. 예를 들어 이라고 하는 웹 사이트 **mysite** 및 라는 슬롯이 **테스트** URI는 `mysite-test.cloudapp.net`, 하지만 구성 파일에 사용할 올바른 이름은 mysite (test). 작업만 수행할 수 있습니다이 경우 웹 사이트 및 슬롯 구독에 이미 존재 합니다. 없는 경우 웹 사이트를 만든 슬롯을 지정 하지 않고 스크립트를 실행 하 여 만든 슬롯에는 [Azure portal](https://portal.azure.com/), 수정한 웹 사이트 이름을 사용 하 여 스크립트를 실행 합니다. 웹 앱 배포 슬롯에 대 한 자세한 내용은 참조 하세요. [Azure App Service에서 웹 앱 용 스테이징 환경 설정](/azure/app-service/web-sites-staged-publishing)합니다.

## <a name="how-to-run-the-publish-scripts"></a>게시 스크립트를 실행 하는 방법

하기 전에 Windows PowerShell 스크립트를 실행 한 적, 스크립트를 실행할 수 있도록 실행 정책을 먼저 설정 해야 합니다. 정책에는 사용자가 맬웨어 또는 스크립트를 실행 하는 바이러스에 취약 한 경우 Windows PowerShell 스크립트를 실행 하지 못하도록 보안 기능입니다.

### <a name="run-the-script"></a>스크립트를 실행 합니다.

1. 프로젝트에 대 한 웹 배포 패키지를 만듭니다. 웹 배포 패키지는 웹 사이트 또는 가상 머신에 복사 하려는 파일이 포함 된 압축된 아카이브 (.zip 파일). 모든 웹 응용 프로그램에 대 한 Visual Studio에서 웹 배포 패키지를 만들 수 있습니다.

   ![웹 만들 패키지 배포](./media/vs-azure-tools-publishing-using-powershell-scripts/IC767885.png)

   자세한 내용은 [방법: Visual Studio에서 웹 배포 패키지 만들기](https://msdn.microsoft.com/library/dd465323.aspx)합니다. 에 설명 된 대로 웹 배포 패키지 만들기를 자동화할 수도 있습니다 [사용자 지정 및 게시 스크립트를 확장](#customizing-and-extending-publish-scripts)합니다.

1. **솔루션 탐색기**선택한을 스크립트에 대 한 상황에 맞는 메뉴를 열고 **PowerShell ISE로 열기**합니다.
1. 처음으로이 컴퓨터에 Windows PowerShell 스크립트를 실행 하는 경우 관리자 권한으로 명령 프롬프트 창을 열고 및 다음 명령을 입력 합니다.

    ```powershell
    Set-ExecutionPolicy RemoteSigned
    ```

1. 다음 명령을 사용 하 여 Azure에 로그인 합니다.

    ```powershell
    Add-AzureAccount
    ```

    메시지가 표시 되 면 사용자 이름 및 암호를 제공 합니다.

    Note 스크립트를 자동화 하는 경우 Azure 자격 증명을 제공 하는이 방법이 작동 하지 않습니다. 대신 사용 해야는 `.publishsettings` 파일 자격 증명을 제공 합니다. 한 번만 명령을 사용 하면 **Get-azurepublishsettingsfile** Azure에서 파일을 다운로드 하 여 이후에 **Import-azurepublishsettingsfile** 파일을 가져옵니다. 자세한 지침은 [Azure PowerShell 설치 및 구성 하는 방법을](/powershell/azure/overview)합니다.

1. (선택 사항) 데이터베이스 및 웹 응용 프로그램을 게시 하지 않고 웹 사이트 사용 가상 컴퓨터와 같은 Azure 리소스를 만들려는 경우 합니다 **Publish-WebApplication.ps1** 명령과 **-Configuration**인수는 JSON 구성 파일에 설정 합니다. 이 명령줄 만들 리소스를 확인 하려면 JSON 구성 파일을 사용 합니다. 다른 명령줄 인수에 대 한 기본 설정을 사용 하기 때문에 리소스를 만들지만 웹 응용 프로그램을 게시 하지 않습니다. – Verbose 옵션은 상황에 대 한 자세한 정보를 제공 합니다.

    ```powershell
    Publish-WebApplication.ps1 -Verbose –Configuration C:\Path\WebProject-WAWS-dev.json
    ```

1. 사용 된 **Publish-WebApplication.ps1** 스크립트를 호출 하 고 웹 응용 프로그램을 게시 하려면 다음 예제 중 하나에 표시 된 대로 명령입니다. 구독 이름과 같은 다른 인수에 대 한 기본 설정을 재정의 패키지 이름, 가상 머신 자격 증명 또는 데이터베이스 서버 자격 증명을 게시 해야 할 경우에 이러한 매개 변수를 지정할 수 있습니다. 사용 된 **– Verbose** 게시 프로세스의 진행률에 대 한 자세한 정보를 보는 옵션입니다.

    ```powershell
    Publish-WebApplication.ps1 –Configuration C:\Path\WebProject-WAWS-dev-json `
    –SubscriptionName Contoso `
    -WebDeployPackage C:\Documents\Azure\ADWebApp.zip `
    -DatabaseServerPassword @{Name="dbServerName";Password="adminPassword"} `
    -Verbose
    ```

    가상 컴퓨터를 만드는 경우 명령은 다음과 같습니다. 이 예제에는 여러 데이터베이스에 대 한 자격 증명을 지정 하는 방법을 보여 줍니다. 이러한 스크립트가 만드는 가상 컴퓨터에서 SSL 인증서를 신뢰할 수 있는 루트 인증 기관의 하지 않습니다. 따라서 사용 해야 합니다 **– AllowUntrusted** 옵션입니다.

    ```powershell
    Publish-WebApplication.ps1 `
    -Configuration C:\Path\ADVM-VM-test.json `
    -SubscriptionName Contoso `
    -WebDeployPackage C:\Path\ADVM.zip `
    -AllowUntrusted `
    -VMPassword @{name = "vmUserName"; password = "YourPasswordHere"} `
    -DatabaseServerPassword @{Name="server1";Password="adminPassword1"}, @{Name="server2";Password="adminPassword2"} `
    -Verbose
    ```

    스크립트에 데이터베이스를 만들 수 있지만 데이터베이스 서버를 만들지 않습니다. 데이터베이스 서버를 만들려는 경우 사용할 수 있습니다 합니다 **New-azuresqldatabaseserver** Azure 모듈의 함수입니다.

## <a name="customizing-and-extending-the-publish-scripts"></a>사용자 지정 및 게시 스크립트를 확장 합니다.

게시 스크립트 및 JSON 구성 파일을 사용자 지정할 수 있습니다. Windows PowerShell 모듈의 함수 **AzureWebAppPublishModule.psm1** 수정할 수는 없습니다. 다른 데이터베이스를 지정 하거나 가상 컴퓨터의 속성 중 일부를 변경 하 고 싶으면 JSON 구성 파일을 편집 합니다. 빌드 및 프로젝트 테스트를 자동화 하도록 스크립트 기능을 확장 하려는 경우에 함수 스텁의 구현할 수 있습니다 **Publish-WebApplication.ps1**합니다.

프로젝트 빌드를 자동화 하기 위해 MSBuild를 호출 하는 코드를 추가 `New-WebDeployPackage` 이 코드 예제에 표시 된 대로 합니다. MSBuild 명령에 대 한 경로 설치한 Visual Studio의 버전에 따라 다릅니다. 올바른 경로 가져오려면 함수를 사용할 수 있습니다 **Get-msbuildcmd**이 예제에서 보여준 것 처럼 합니다.

### <a name="to-automate-building-your-project"></a>프로젝트 빌드를 자동화 하려면

1. 추가 된 `$ProjectFile` 전역 param 섹션에 매개 변수입니다.

    ```powershell
    [Parameter(Mandatory = $false)]
    [ValidateScript({Test-Path $_ -PathType Leaf})]
    [String]
    $ProjectFile,
    ```

1. 함수 복사 `Get-MSBuildCmd` 스크립트 파일에 있습니다.

    ```powershell
    function Get-MSBuildCmd
    {
            process
    {

                $path =  Get-ChildItem "HKLM:\SOFTWARE\Microsoft\MSBuild\ToolsVersions\" |
                                    Sort-Object {[double]$_.PSChildName} -Descending |
                                    Select-Object -First 1 |
                                    Get-ItemProperty -Name MSBuildToolsPath |
                                    Select -ExpandProperty MSBuildToolsPath

                $path = (Join-Path -Path $path -ChildPath 'msbuild.exe')

            return Get-Item $path
        }
    }
    ```

1. 바꿉니다 `New-WebDeployPackage` 사용 하 여 다음 코드로 바꾸고 생성 줄에서 자리 표시자 `$msbuildCmd`합니다. 이 코드는 Visual Studio 2015 용입니다. Visual Studio 2017을 사용 하는 경우 변경 합니다 **VisualStudioVersion** 속성을 `15.0` (`12.0` Visual Studio 2013 용).

    ```powershell
    function New-WebDeployPackage
    {
        #Write a function to build and package your web application
    ```

    웹 응용 프로그램을 빌드하려면 MsBuild.exe를 사용 합니다. MSBuild 명령줄 참조를 참조 하세요. [http://go.microsoft.com/fwlink/?LinkId=391339](http://go.microsoft.com/fwlink/?LinkId=391339)

    ```powershell
    Write-VerboseWithTime 'Build-WebDeployPackage: Start'

    $msbuildCmd = '"{0}" "{1}" /T:Rebuild;Package /P:VisualStudioVersion=14.0 /p:OutputPath="{2}\MSBuildOutputPath" /flp:logfile=msbuild.log,v=d' -f (Get-MSBuildCmd), $ProjectFile, $scriptDirectory

    Write-VerboseWithTime ('Build-WebDeployPackage: ' + $msbuildCmd)
    ```

### <a name="start-execution-of-the-build-command"></a>빌드 명령 실행 시작

```powershell
$job = Start-Process cmd.exe -ArgumentList('/C "' + $msbuildCmd + '"') -WindowStyle Normal -Wait -PassThru

if ($job.ExitCode -ne 0) {
    throw('MsBuild exited with an error. ExitCode:' + $job.ExitCode)
}

#Obtain the project name
$projectName = (Get-Item $ProjectFile).BaseName

#Construct the path to web deploy zip package
$DeployPackageDir =  '.\MSBuildOutputPath\_PublishedWebsites\{0}_Package\{0}.zip' -f $projectName

#Get the full path for the web deploy zip package. This is required for MSDeploy to work
$WebDeployPackage = Resolve-Path –LiteralPath $DeployPackageDir

Write-VerboseWithTime 'Build-WebDeployPackage: End'

return $WebDeployPackage
}
```

1. 호출 된 `New-WebDeployPackage` 이 줄 앞에 함수: `$Config = Read-ConfigFile $Configuration` 웹 앱에 대 한 또는 `$Config = Read-ConfigFile $Configuration -HasWebDeployPackage:([Bool]$WebDeployPackage)` 가상 머신에 대 한 합니다.

    ```powershell
    if($ProjectFile)
    {
    $WebDeployPackage = New-WebDeployPackage
    }
    ```

1. 전달을 사용 하 여 명령줄에서 사용자 지정된 스크립트를 호출 합니다 `$Project` 다음 예제와 같이 인수:

    ```powershell
    .\Publish-WebApplicationVM.ps1 -Configuration .\Configurations\WebApplication5-VM-dev.json `
    -ProjectFile ..\WebApplication5\WebApplication5.csproj `
    -VMPassword @{Name="VMUser";Password="Test.123"} `
    -AllowUntrusted `
    -Verbose
    ```

    응용 프로그램의 테스트 자동화 코드를 추가 `Test-WebApplication`합니다. 줄에서 주석 처리를 제거 해야 **Publish-WebApplication.ps1** 이러한 함수가 호출 됩니다. 구현을 제공 하지 않으면, 수동으로 Visual Studio를 사용 하 여 프로젝트를 빌드할 수 있으며 그런 다음 게시 스크립트를 Azure에 게시할 수 있습니다.

## <a name="publishing-function-summary"></a>게시 함수 요약
Windows PowerShell 명령 프롬프트에서 사용할 수 있는 함수에 대 한 도움말을 보려면 명령을 사용 하 여 `Get-Help function-name`입니다. 도움말에는 매개 변수 도움말과 예제가 포함 됩니다. 동일한 도움말 텍스트가 스크립트 원본 파일 역시 **AzureWebAppPublishModule.psm1** 하 고 **Publish-WebApplication.ps1**합니다. 스크립트와 도움말은 Visual Studio 언어로 지역화 됩니다.

**AzureWebAppPublishModule**

| 함수 이름 | 설명 |
| --- | --- |
| 추가 AzureSQLDatabase |새 Azure SQL database를 만듭니다. |
| Add-azuresqldatabases |Visual Studio에서 생성 하는 JSON 구성 파일 값에서 Azure SQL database를 만듭니다. |
| Add-azurevm |Azure 가상 머신을 만들고 배포 된 VM의 URL을 반환 합니다. 함수는 필수 구성 요소를 호출 합니다 **New-azurevm** 새 가상 컴퓨터를 만드는 함수 (Azure 모듈). |
| Add-azurevmendpoints |가상 머신에 새 입력된 끝점을 추가 하 고 새 끝점을 사용 하 여 가상 컴퓨터를 반환 합니다. |
| Add-azurevmstorage |현재 구독에서 새 Azure storage 계정을 만듭니다. 계정 이름 뒤에 고유한 영숫자 문자열이 "devtest"로 시작 합니다. 함수에는 새 저장소 계정의 이름을 반환합니다. 위치 또는 새 저장소 계정에 대 한 선호도 그룹을 지정 합니다. |
| Add-azurewebsite |지정한 이름 및 위치를 사용 하 여 웹 사이트를 만듭니다. 이 함수를 호출 합니다 **New-azurewebsite** Azure 모듈의 함수입니다. 에 없으면 구독이 이미 지정 된 이름의 웹 사이트를이 함수는 웹 사이트를 만들고 웹 사이트 개체를 반환 합니다. 그 외의 경우 `$null`를 반환합니다. |
| 백업 구독 |에 현재 Azure 구독을 저장 합니다 `$Script:originalSubscription` 스크립트 범위 변수입니다. 이 함수는 현재 Azure 구독을 저장 (에서 가져온 대로 `Get-AzureSubscription -Current`) 및 해당 저장소 계정 및이 스크립트로 변경 된 구독 (변수에 저장 된 `$UserSpecifiedSubscription`) 및 해당 저장소 계정을 스크립트 범위에 있습니다. 값을 저장 하 여 사용할 수는 함수 같은 `Restore-Subscription`를 현재 상태가 변경 되 면 원래 현재 구독과 저장소 계정을 현재 상태로 복원 합니다. |
| Find-azurevm |지정된 된 Azure 가상 컴퓨터를 가져옵니다. |
| Format-devtestmessagewithtime |날짜 및 시간을 메시지에 추가합니다. 이 함수는 오류 및 자세한 정보 표시 스트림에 기록 된 메시지에 대 한 설계 되었습니다. |
| Get-AzureSQLDatabaseConnectionString |Azure SQL database에 연결 하기 위한 연결 문자열을 어셈블합니다. |
| Get-azurevmstorage |이름 패턴을 사용 하 여 첫 번째 저장소 계정의 이름을 반환 합니다 "devtest *" (대/소문자 구분)에 지정 된 위치 또는 선호도 그룹. 경우는 "devtest*" 저장소 계정이 위치나 선호도 그룹과 일치 하지 않습니다, 함수가를 무시 합니다. 위치 또는 선호도 그룹을 지정 합니다. |
| Get-msdeploycmd |MsDeploy.exe 도구를 실행 하는 명령을 반환 합니다. |
| New-azurevmenvironment |찾거나 JSON 구성 파일에서 값과 일치 하는 구독에서 가상 컴퓨터를 만듭니다. |
| Publish-webpackage |사용 하 여 MsDeploy.exe 및 웹 패키지를 게시 합니다. Zip 파일을 웹 사이트에 리소스를 배포 합니다. 이 함수는 어떠한 출력도 생성 하지 않습니다. MSDeploy.exe에 대 한 호출에 실패 하면 함수는 예외를 throw 합니다. 자세한 출력을 사용 합니다 **-Verbose** 옵션입니다. |
| Publish-webpackagetovm |매개 변수 값을 확인 하 고 호출 하 여 **Publish-webpackage** 함수입니다. |
| 읽기-ConfigFile |JSON 구성 파일의 유효성을 검사 하 고 선택한 값의 해시 테이블을 반환 합니다. |
| 복원-구독 |원래 구독에 현재 구독을 다시 설정합니다. |
| Test-azuremodule |반환 `$true` 경우 설치 된 Azure 모듈 버전이 0.7.4 이상. 반환 `$false` 모듈 설치 되지 않았거나 이전 버전이 면 합니다. 이 함수에 매개 변수가 없습니다. |
| 테스트 AzureModuleVersion |반환 `$true` 경우 Azure 모듈 버전이 0.7.4 이상. 반환 `$false` 모듈 설치 되지 않았거나 이전 버전이 면 합니다. 이 함수에 매개 변수가 없습니다. |
| 테스트 HttpsUrl |입력된 URL을 System.Uri 개체로 변환합니다. 반환 `$True` URL이 절대 주소 및 해당 스키마가 https 인 경우. 반환 `$false` 경우 URL은 상대, 해당 스키마가 HTTPS, 또는 입력된 문자열을 URL로 변환할 수 없습니다. |
| 테스트 멤버 |반환 `$true` 속성 또는 메서드를 개체의 구성원 인 경우. 그렇지 않으면 `$false`를 반환합니다. |
| 쓰기 ErrorWithTime |현재 시간을 접두사로 하는 오류 메시지를 씁니다. 이 함수를 호출 합니다 **Format-devtestmessagewithtime** 오류 스트림으로 메시지를 쓰기 전의 시간을 앞에 추가 하는 함수입니다. |
| 쓰기 HostWithTime |호스트 프로그램에 메시지를 씁니다 (**Write-host**) 현재 시간이 맨 앞입니다. 호스트 프로그램에 쓰는 효과 달라 집니다. 대부분의 프로그램 Windows PowerShell 호스트 하는 표준 출력으로 이러한 메시지를 씁니다. |
| 쓰기 VerboseWithTime |현재 시간을 접두사로 하는 자세한 정보 메시지를 씁니다. 호출 하므로 **Write-verbose**, 스크립트를 실행할 때만 사용 하 여 메시지를 표시 합니다 **Verbose** 매개 변수 때나 합니다 **VerbosePreference** 기본설정이설정되어 **계속**합니다. |

**게시 웹 응용 프로그램**

| 함수 이름 | 설명 |
| --- | --- |
| 새 AzureWebApplicationEnvironment |웹 사이트 또는 가상 컴퓨터와 같은 Azure 리소스를 만듭니다. |
| 새 WebDeployPackage |이 함수는 구현 되지 않습니다. 프로젝트를 빌드하려면이 함수에 명령을 추가할 수 있습니다. |
| 게시 AzureWebApplication |Azure 웹 응용 프로그램을 게시합니다. |
| 게시 웹 응용 프로그램 |만들고 Web Apps, virtual machines, SQL 데이터베이스 및 Visual Studio 웹 프로젝트에 대 한 저장소 계정을 배포 합니다. |
| 테스트-웹 응용 프로그램 |이 함수는 구현 되지 않습니다. 응용 프로그램을 테스트 하려면이 함수에 명령을 추가할 수 있습니다. |

## <a name="next-steps"></a>다음 단계
읽어 PowerShell 스크립팅에 대해 자세히 알아보십시오 [Windows PowerShell을 사용한 스크립팅](https://technet.microsoft.com/library/bb978526.aspx) 에서 다른 Azure PowerShell 스크립트를 참조 하 고는 [스크립트 센터](https://azure.microsoft.com/documentation/scripts/)합니다.
