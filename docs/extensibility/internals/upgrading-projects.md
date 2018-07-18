---
title: 프로젝트 업그레이드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- upgrading VSPackages
- upgrading applications, strategies
- VSPackages, upgrade support
ms.assetid: e01cb44a-8105-4cf4-8223-dfae65f8597a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ea5c29819d0035e45f97122fd108ea1f51d60806
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057536"
---
# <a name="upgrading-projects"></a>프로젝트 업그레이드

다음에 한 버전의 Visual Studio에서 프로젝트 모델의 변경 내용을 최신 버전에서 실행할 수 있도록 프로젝트 및 솔루션 업그레이드 될 필요할 수 있습니다. [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 지원을 구현 하기 위해 업그레이드 자체 프로젝트에서 사용할 수 있는 인터페이스를 제공 합니다.

## <a name="upgrade-strategies"></a>업그레이드 전략

업그레이드를 지원 하기 위해 프로젝트 시스템 구현을 정의 하 고 업그레이드 전략을 구현 해야 합니다. 전략을 결정 하는 데,--나란히 (SxS) 백업, 복사 백업 중 하나 또는 둘 다 지원 하기 위해 선택할 수 있습니다.

-   SxS 백업 프로젝트를 직접 업그레이드에 적합 한 파일 이름 접미사를 예를 들어 추가 ".old" 해야 하는 파일만 복사를 의미 합니다.

-   복사 백업 프로젝트를 사용자가 제공한 백업 위치에 모든 프로젝트 항목을 복사 하는 것을 의미 합니다. 원래 프로젝트 위치에서 관련 파일을 업그레이드 한 다음 됩니다.

## <a name="how-upgrade-works"></a>업그레이드가 작동 하는 방법

최신 버전의 Visual Studio의 이전 버전에서 만든 솔루션을 열면 IDE로 업그레이드 해야 하는 경우를 확인 하려면 솔루션 파일을 확인 합니다. 업그레이드 하는 것이 필요 합니다 **업그레이드 마법사** 업그레이드 프로세스를 통해 사용자를 자동으로 시작 됩니다.

솔루션에서 업그레이드 필요한 경우 각 프로젝트 팩터리 해당 업그레이드 전략에 대해 쿼리 합니다. 전략은 프로젝트 팩터리 복사본 또는 SxS 백업 지원 하는지 여부를 결정 합니다. 정보를 보낼 합니다 **업그레이드 마법사**, 백업에 필요한 정보를 수집 하 고 사용자에 게 해당 옵션을 제공 합니다.

### <a name="multi-project-solutions"></a>다중 프로젝트 솔루션

솔루션을 여러 프로젝트를 포함 하며 SxS 백업과 웹만 지 원하는 c + + 프로젝트만 해당 지원 복사 백업 프로젝트 하는 경우 같은 업그레이드 전략 다를 경우 프로젝트 팩터리 업그레이드 전략을 조정 해야 합니다.

솔루션에 대 한 각 프로젝트 팩터리 쿼리 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>합니다. 그런 다음 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject_CheckOnly%2A> 전역 프로젝트 파일에 업그레이드 해야 하는지 확인 하 고 지원 되는 업그레이드 전략을 확인할 수 있습니다. 합니다 **업그레이드 마법사** 후 호출 됩니다.

사용자가 마법사를 완료 한 후 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 실제 업그레이드를 수행 하려면 각 프로젝트 팩터리에서 라고 합니다. 백업을 용이 하 게 하려면 IVsProjectUpgradeViaFactory 메서드를 제공 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> 서비스 업그레이드 프로세스의 세부 정보를 기록 합니다. 이 서비스를 캐시할 수 없습니다.

관련 된 모든 전역 파일을 업데이트 한 후 각 프로젝트 팩터리 프로젝트를 인스턴스화할 수 있습니다. 프로젝트 지원 되어야 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 모든 관련 프로젝트 항목 업그레이드 메서드가 호출 됩니다.

> [!NOTE]
> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 메서드 SVsUpgradeLogger 서비스를 제공 하지 않습니다. 이 서비스를 호출 하 여 얻을 수 있습니다 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>합니다.

## <a name="best-practices"></a>모범 사례

사용 된 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> 를 편집 하기 전에 파일을 편집할 수를 저장 하기 전에 저장할 수를 확인 하는 서비스입니다. 이렇게 하면 백업 및 소스 제어에서 프로젝트 파일, 권한 부족 등을 사용 하 여 파일을 처리 하는 업그레이드 구현 합니다.

사용 된 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> 백업의 모든 단계 서비스 및 업그레이드 프로세스의 성공 여부에 대 한 정보를 업그레이드 합니다.

백업 및 프로젝트를 업그레이드 하는 방법에 대 한 자세한 내용은 IVsProjectUpgrade 주석을 vsshell2.idl에서 참조 하십시오.

## <a name="upgrading-custom-projects"></a> 사용자 지정 프로젝트 업그레이드

제품의 다른 Visual Studio 버전 간에 프로젝트 파일에 있는 정보를 변경하는 경우 이전 버전에서 새 버전으로의 프로젝트 파일 업그레이드를 지원해야 합니다. 참여할 수 있도록 업그레이드를 지원 합니다 **Visual Studio 변환 마법사**를 구현를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스입니다. 이 인터페이스에는 복사 업그레이드에 사용할 수 있는 메커니즘만 포함되어 있습니다. 프로젝트 업그레이드는 솔루션의 일부가 열릴 때 수행됩니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스 프로젝트 팩터리에서 구현 되거나 프로젝트 팩터리에서 얻을 수 있는 최소 여야 합니다.

사용 하는 이전 메커니즘은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 인터페이스는 계속 지원 하지만 개념적으로 열린 프로젝트의 일부로 프로젝트 시스템을 업그레이드 합니다. 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 경우에도 Visual Studio 환경에서 따라서 라고 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스가 호출 또는 구현 합니다. 이 방법을 사용할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 을 복사를 구현 하 고 업그레이드의 일부분에만 프로젝트에서-에서 바로 (아마도 새 위치)를 수행 해야 하는 작업의 나머지 부분에서 대리자를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 인터페이스입니다.

샘플 구현은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>를 참조 하세요 [VSSDK 샘플](http://aka.ms/vs2015sdksamples)합니다.

프로젝트 업그레이드에서는 다음과 같은 시나리오가 발생합니다.

-   파일이 프로젝트에서 지원할 수 있는 형식보다 최신 형식인 경우 이를 설명하는 오류를 반환해야 합니다. 이 이전 버전의 제품 버전에 대 한 확인 하는 코드가 포함을 가정 합니다.

-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_SXSBACKUP> 플래그가 지정 된는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 메서드 업그레이드 프로젝트를 열기 전에 현재 위치 업그레이드로 구현 될 것입니다.

-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_COPYBACKUP> 플래그가 지정 된 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 메서드에 복사 업그레이드로 구현 됩니다.

-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> 플래그가 지정 된 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 호출에 되었습니다 하 라는 메시지가 환경에서 프로젝트를 연 후 프로젝트 파일의 전체 업그레이드를로 업그레이드 합니다. 예를 들어 사용자가 이전 버전의 솔루션을 여는 경우 업그레이드하라는 메시지가 표시됩니다.

-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> 플래그에 지정 되어 있지는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 호출에 사용자에 게 프로젝트 파일 업그레이드를 요청 해야 합니다.

     다음은 업그레이드 프롬프트 메시지의 예입니다.

     "'%1' 프로젝트는 이전 버전의 Visual Studio에서 만들었습니다. 이 버전의 Visual Studio에서 이 프로젝트를 열면 이전 버전의 Visual Studio에서 이 프로젝트를 열 수 없습니다. 이 프로젝트를 계속 여시겠습니까?”

### <a name="to-implement-ivsprojectupgradeviafactory"></a>IVsProjectUpgradeViaFactory를 구현하려면

1.  메서드를 구현 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스를 구체적으로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 프로젝트 팩터리 구현에서 메서드 또는 구현 프로젝트 팩터리 구현에서 호출할 수.

2.  솔루션 열기의 일부로 현재 위치 업그레이드를 수행 하려는 경우이 플래그를 제공 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_SXSBACKUP> 으로 `VSPUVF_FLAGS` 매개 변수에서 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 구현 합니다.

3.  솔루션 열기의 일부로 현재 위치 업그레이드를 수행 하려는 경우이 플래그를 제공 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_COPYBACKUP> 으로 `VSPUVF_FLAGS` 매개 변수에서 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 구현 합니다.

4.  두 단계를 2와 3에 대 한 실제 파일 업그레이드 단계를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>에 설명 된 대로 구현할 수 있습니다는 "구현 `IVsProjectUpgade`" 섹션 아래에서 또는 실제 파일 업그레이드를 위임할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>합니다.

5.  메서드를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> 업그레이드 후에 Visual Studio 마이그레이션 마법사를 사용 하 여 사용자에 대 한 메시지를 관련 됩니다.

6.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileUpgrade> 모든 종류의 프로젝트 업그레이드의 일부로 수행 해야 하는 파일 업그레이드를 구현 하는 인터페이스가 사용 됩니다. 이 인터페이스에서 호출 되지 않습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>, 프로젝트 시스템, 하지만 기본 프로젝트 시스템의 일부인 파일을 업그레이드 하는 메커니즘의 직접 알지 못할 제공 됩니다. 예를 들어 나머지 프로젝트 시스템을 처리하는 개발 팀이 컴파일러 관련 파일 및 속성을 처리하지 않는 경우 이러한 상황이 발생할 수 있습니다.

### <a name="ivsprojectupgrade-implementation"></a>IVsProjectUpgrade 구현

프로젝트 시스템을 구현 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 만에 참여 하지 수 합니다 **Visual Studio 변환 마법사**합니다. 그러나 구현 하는 경우에 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스를 위임할 수 있습니다 여전히 파일 업그레이드를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 구현 합니다.

#### <a name="to-implement-ivsprojectupgrade"></a>IVsProjectUpgrade를 구현하려면

1.  사용자는 프로젝트를 열려고 할 때를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 프로젝트가 열린 후 다른 사용자 전에 조치를 취할 수 프로젝트 환경 메서드를 호출 합니다. 사용자가 이미 된 메시지가 표시 되 면 솔루션을 업그레이드 하는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> 에 플래그를 전달 하는 `grfUpgradeFlags` 매개 변수입니다. 사용자가 프로젝트를 직접 이러한 경우 사용 하는 **기존 프로젝트 추가** 명령인 경우 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS.UPF_SILENTMIGRATE> 플래그가 전달 되지 않으며 프로젝트를 업그레이드 하 라는 메시지를 해야 합니다.

2.  에 대 한 응답을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 호출 프로젝트는 프로젝트 파일을 업그레이드 여부를 평가 해야 합니다. 프로젝트는 프로젝트 형식을 새 버전으로 업그레이드할 필요가 없습니다 경우 반환할 수는 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 플래그입니다.

3.  프로젝트 해야 프로젝트 형식을 새 버전으로 업그레이드할 경우 호출 하 여 프로젝트 파일을 수정할 수 있는지 여부를 확인 해야 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 메서드 및 값을 전달 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags> 에 대 한는 `rgfQueryEdit` 매개 변수. 그런 다음 프로젝트에서 다음을 수행해야 합니다.

    -   경우는 `VSQueryEditResult` 에서 반환 된 값을 `pfEditCanceled` 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditOK>, 다음 프로젝트 파일을 쓸 수 있으므로 업그레이드를 진행할 수 있습니다.

    -   경우는 `VSQueryEditResult` 에서 반환 된 값을 `pfEditCanceled` 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> 및 `VSQueryEditResult` 값에는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyNotUnderScc> 비트가 설정 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 사용자 권한 문제를 직접 해결 해야 하기 때문에 오류를 반환 해야 합니다. 그런 다음 프로젝트에서 다음을 수행해야 합니다.

         호출 하 여 사용자에 게 오류를 보고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> 반환 된 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED> 오류 코드를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>입니다.

    -   경우는 `VSQueryEditResult` 값이 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> 및 `VSQueryEditResultFlags` 값에는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyUnderScc> 호출 하 여 프로젝트 파일을 체크 아웃할 수는 비트가 설정 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ForceEdit_NoPrompting>, <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_DisallowInMemoryEdits>,...).

4.  경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 프로젝트 파일에서 호출 하면 파일을 체크 아웃 되 고 최신 버전을 검색할 수 다음 프로젝트를 언로드 했다가 다시 로드 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 프로젝트의 다른 인스턴스가 생성 되 면 메서드가 다시 호출 됩니다. 이 두 번째 호출에서 프로젝트 파일을 디스크에 쓸 수 있습니다. 프로젝트에서 프로젝트 파일의 복사본을 .OLD 확장명을 사용하는 이전 형식으로 저장하고 필요한 업그레이드 변경을 수행한 다음 프로젝트 파일을 새 형식으로 저장하는 것이 좋습니다. 마찬가지로 업그레이드 프로세스의 일부가 실패 하면 메서드 나타내야 오류를 반환 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED>입니다. 이로 인해 솔루션 탐색기에서 프로젝트가 언로드됩니다.

     사례에 대 한 환경에서 발생 하는 전체 프로세스를 이해 해야 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 메서드 (ReportOnly 값 지정)를 반환 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> 및 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyUnderScc> 플래그.

5.  사용자가 프로젝트 파일을 열려고 합니다.

6.  환경에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> 구현 합니다.

7.  경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> 반환 `true`, 다음 환경에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> 구현 합니다.

8.  환경에 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A> Project1 파일을 열고 예를 들어, 프로젝트 개체를 초기화 하려면 구현 합니다.

9. 환경에서 `IVsProjectUpgrade::UpgradeProject` 구현을 호출하여 프로젝트 파일을 업그레이드해야 하는지 여부를 확인합니다.

10. 문의할 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 의 값을 전달 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ReportOnly> 에 대 한는 `rgfQueryEdit` 매개 변수입니다.

11. 환경 반환 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditNotOK> 에 대 한 `VSQueryEditResult` 하며 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags.QER_ReadOnlyUnderScc> 에 비트가 설정 `VSQueryEditResultFlags`합니다.

12. 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 구현 호출 `IVsQueryEditQuerySave::QueryEditFiles` (<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ForceEdit_NoPrompting>, <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_DisallowInMemoryEdits>).

이 호출로 인해 프로젝트 파일의 새 복사본이 체크 아웃되고 최신 버전이 검색될 수 있으며 프로젝트 파일을 다시 로드해야 합니다. 이때 다음 두 가지 중 하나가 발생합니다.

-   프로젝트 다시 로드를 처리 하는 경우 다음 환경 호출 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> (VSITEMID_ROOT) 구현을 합니다. 이 호출을 받는 경우 프로젝트의 첫 번째 인스턴스(Project1)를 다시 로드하고 계속 프로젝트 파일을 업그레이드합니다. 환경 반환 하는 경우 사용자 고유의 프로젝트 다시 로드를 처리 한다고 인식 `true` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID.VSHPROPID_HandlesOwnReload>).

-   사용자 고유의 프로젝트 다시 로드를 처리 하지 않는 경우 돌아가게 `false` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID.VSHPROPID_HandlesOwnReload>). 이 경우 이전 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>(QEF_ForceEdit_NoPrompting, QEF_DisallowInMemoryEdits) 반환 환경의 예를 들어 Project2 프로젝트의 다른 새 인스턴스를 다음과 같이 만듭니다.

    1.  환경 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.Close%2A> 첫 번째 프로젝트 개체 Project1에 있으므로이 개체에에서 배치 비활성 상태입니다.

    2.  환경에서 `IVsProjectFactory::CreateProject` 구현하여 프로젝트의 두 번째 인스턴스 Project2를 만듭니다.

    3.  환경에서 `IPersistFileFormat::Load` 구현을 호출하여 파일을 열고 두 번째 프로젝트 개체 Project2를 초기화합니다.

    4.  환경에서 `IVsProjectUpgrade::UpgradeProject` 를 두 번째로 호출하여 프로젝트 개체를 업그레이드해야 하는지 여부를 결정합니다. 그러나 이 호출은 프로젝트의 새로운 두 번째 인스턴스 Project2에 대해 수행됩니다. 이 프로젝트가 솔루션에 열려 있는 프로젝트입니다.

        > [!NOTE]
        > 첫 번째 프로젝트 Project1이 비활성 상태에 배치 됩니다을 반환 해야 하는 인스턴스의 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 를 호출 하 여 첫 번째 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 구현 합니다.

    5.  문의할 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 의 값을 전달 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags.QEF_ReportOnly> 에 대 한는 `rgfQueryEdit` 매개 변수입니다.

    6.  환경 반환 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult.QER_EditOK> 및 프로젝트 파일을 쓸 수 있으므로 업그레이드를 진행할 수 있습니다.

을 업그레이드 하지 못하면 반환 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED> 에서 `IVsProjectUpgrade::UpgradeProject`합니다. 업그레이드가 필요하지 않거나 업그레이드하지 않으려면 `IVsProjectUpgrade::UpgradeProject` 호출을 no-op으로 처리합니다. 반환 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes.VS_E_PROJECTMIGRATIONFAILED>, 자리 표시자 노드가 솔루션에 프로젝트가 추가 됩니다.

## <a name="upgrading-project-items"></a>프로젝트 항목 업그레이드

를 추가 하거나 구현 하지 않는 프로젝트 시스템 내에서 항목을 관리 하는 경우 프로젝트 업그레이드 프로세스에 참여 해야 합니다. Crystal Reports은 프로젝트 시스템에 추가할 수 있는 항목의 예입니다.

일반적으로 프로젝트 항목 구현자는 어떤 프로젝트 참조 및 기타 프로젝트 속성 있습니다 업그레이드 결정을 내리는 데 알아야 하므로 이미 완전히 인스턴스화된 및 업그레이드 된 프로젝트를 활용 하려고 합니다.

### <a name="to-get-the-project-upgrade-notification"></a>프로젝트 업그레이드 알림을 가져올

1.  설정 된 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80.SolutionOrProjectUpgrading> 프로젝트 항목 구현에서 플래그 (vsshell80.idl에 정의 됨). 이렇게 하면 프로젝트 시스템 업그레이드 프로세스는 Visual Studio shell을 결정 하는 경우 VSPackage 프로젝트 항목 자동 로드 합니다.

2.  Advise 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 인터페이스를 통해를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution2.AdviseSolutionEvents%2A> 메서드.

3.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 인터페이스 프로젝트 시스템 구현을 업그레이드 작업을 완료 하 고 새 업그레이드 된 프로젝트가 만들어진 후 발생 합니다. 시나리오에 따라를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 인터페이스 후 발생 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A>의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>, 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> 메서드.

### <a name="to-upgrade-the-project-item-files"></a>프로젝트 항목 파일을 업그레이드 하려면

1.  프로젝트 항목 구현에서 파일 백업 프로세스를 신중 하 게 관리 해야 합니다. Side-by-side-백업에 대 한 특히 적용이 위치는 `fUpgradeFlag` 의 매개 변수를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 방법은로 설정 되어 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS.PUVFF_SXSBACKUP>".old"으로 지정 된 클라이언트측 파일에 따라 백업 된 파일 위치, 합니다. 시퀀스 번호가 오래 되어 프로젝트를 업그레이드 하는 경우 시스템 시간 보다 오래 된 백업된 파일을 지정할 수 있습니다. 또한 이러한이 방지 하기 위한 특정 단계를 수행 하지 않으면 덮어쓸 수 있습니다.

2.  프로젝트 항목의 프로젝트 업그레이드에 대 한 알림을 가져옵니다 시점에는 **Visual Studio 변환 마법사** 계속 표시 됩니다. 메서드를 사용 해야 하므로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> 마법사 UI 업그레이드 메시지를 제공 하는 인터페이스입니다.

## <a name="see-also"></a>참고자료

- [프로젝트](../../extensibility/internals/projects.md)