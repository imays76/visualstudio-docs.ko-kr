---
title: 관리 되는 코드의 HRESULT 정보 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSPackages, HRESULT information
- HRESULT, managed VSPackages
ms.assetid: 0795ee94-17a8-4327-bf57-27cd5e312a4c
caps.latest.revision: 29
manager: douge
ms.openlocfilehash: c87fc618f1c80b60bbd2f95537dc70a83eb2bdc7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541938"
---
# <a name="hresult-information-in-managed-code"></a>관리 되는 코드의 HRESULT 정보
HRESULT 반환 값을 발견할 경우 관리 코드와 COM 간의 상호 작용으로 인해 문제가 발생할 수 있습니다.  
  
 COM 인터페이스에서 HRESULT 반환 값은 다음과 같은 역할을 할 수 있습니다.  
  
-   오류 정보를 제공 (예를 들어 <xref:Microsoft.VisualStudio.VSConstants.E_INVALIDARG>).  
  
-   일반적인 프로그램 동작에 대한 상태 정보를 제공합니다.  
  
 COM이 관리 코드를 호출하는 경우 HRESULT로 인해 다음과 같은 문제가 발생할 수 있습니다.  
  
-   0보다 작은 HRESULT 값(오류 코드)을 반환하는 COM 함수가 예외를 생성합니다.  
  
-   정기적으로 예를 들어, 두 개 이상의 서로 다른 성공 코드를 반환 하는 COM 메서드 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 또는 <xref:Microsoft.VisualStudio.VSConstants.S_FALSE>를 구분할 수 없습니다.  
  
 때문에 많은 [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] HRESULT 값 보다 작거나 0 또는 다른 성공 코드를 반환 하거나 반환 하는 COM 함수는 [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] interop 어셈블리 메서드 서명이 유지 되도록 작성 되었습니다. 모든 [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] interop 메서드는 `int` 형식입니다. HRESULT 값은 변경 및 예외 생성 없이 interop 계층을 통해 전달됩니다.  
  
 COM 함수는 호출하는 관리되는 메서드에 HRESULT를 반환하므로 호출하는 메서드가 HRESULT를 확인하고 필요에 따라 예외를 발생시켜야 합니다.  
  
## <a name="handling-hresults-returned-to-managed-code-from-com"></a>COM에서 관리 코드로 반환되는 HRESULT 처리  
 관리 코드에서 COM 인터페이스를 호출하는 경우 HRESULT 값을 검사하고 필요에 따라 예외를 발생시킵니다. 합니다 <xref:Microsoft.VisualStudio.ErrorHandler> 클래스를 포함 합니다 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> HRESULT 값에 따라 COM 예외를 throw 하는 메서드를 전달 합니다.  
  
 기본적으로 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 0 보다 작은 값을 가진 HRESULT가 전달 될 때마다 예외를 throw 합니다. 이러한 Hresult가 허용 되는 값 없음 예외를 throw 해야 않았고의 경우 추가 hresult 값에 전달 되어야 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 값이 테스트 된 후입니다. 테스트할 HRESULT 명시적으로 전달 된 HRESULT 값과 일치 하는 경우 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>, 예외가 throw 되지 않습니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.VSConstants> 클래스 일반적인 HRESULT에 대 한 예를 들어 상수를 포함 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 하 고 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>, 및 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] HRESULT, 예를 들어 <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA> 및 <xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>합니다. <xref:Microsoft.VisualStudio.VSConstants> 제공 된 <xref:Microsoft.VisualStudio.ErrorHandler.Succeeded%2A> 및 <xref:Microsoft.VisualStudio.ErrorHandler.Failed%2A> COM.의 SUCCEEDED 및 FAILED 매크로에 해당 하는 방법  
  
 예를 들어 다음 함수 호출은는 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> 는 허용 되는 반환 값 이지만 다른 HRESULT 오류가 0 보다 작은 나타냅니다.  
  
 [!code-csharp[VSSDKHRESULTInformation#1](../snippets/csharp/VS_Snippets_VSSDK/vssdkhresultinformation/cs/vssdkhresultinformationpackage.cs#1)]
 [!code-vb[VSSDKHRESULTInformation#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkhresultinformation/vb/vssdkhresultinformationpackage.vb#1)]  
  
 허용 되는 반환 값을 둘 이상 있는, 경우 추가 HRESULT 값만 추가할 수에 대 한 호출 목록 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>합니다.  
  
 [!code-csharp[VSSDKHRESULTInformation#2](../snippets/csharp/VS_Snippets_VSSDK/vssdkhresultinformation/cs/vssdkhresultinformationpackage.cs#2)]
 [!code-vb[VSSDKHRESULTInformation#2](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkhresultinformation/vb/vssdkhresultinformationpackage.vb#2)]  
  
## <a name="returning-hresults-to-com-from-managed-code"></a>관리 코드에서 COM으로 HRESULT 반환  
 예외가 발생 하는 경우 관리 코드 반환 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 호출한 COM 함수에 있습니다. COM interop는 관리 코드에서 강력한 형식의 일반적인 예외를 지원합니다. 예를 들어 받는 메서드가 있다고는 허용 되지 않는 `null` 인수 throw는 <xref:System.ArgumentNullException>합니다.  
  
 사용할 수 있습니다를 COM에 반환 하려는 HRESULT를 알고 있지만 확실 하지 않은 예외를 발생 시켜야 하는 경우는 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 적절 한 예외를 throw 하는 방법입니다. 예를 들어 비표준 오류를 사용 하더라도 작동 <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>합니다. <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 에 매핑하려고 HRESULT를 강력한 형식의 예외에 전달. 매핑할 수 없는 경우 대신 일반 COM 예외를 발생시킵니다. 최종 결과로 HRESULT에 전달 해야 하는 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 관리 코드에서 호출한 COM 함수에 반환 됩니다.  
  
> [!NOTE]
>  예외가 발생하면 성능이 저하되며 비정상적인 프로그램 상태를 나타냅니다. 자주 발생하는 상태는 예외를 발생시키는 대신 인라인으로 처리해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 되는 Vspackage](../misc/managed-vspackages.md)   
 [비관리 코드와의 상호 운용](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)   
 [방법: Hresult 및 예외 매핑](http://msdn.microsoft.com/library/610b364b-2761-429d-9c4a-afbc3e66f1b9)   
 [상호 운용 위한 COM 구성 요소 빌드](http://msdn.microsoft.com/en-us/7a2c657a-cfef-40f0-bed3-7c2c0ac4abdf)   
 [관리되는 VSPackage](../misc/managed-vspackages.md)