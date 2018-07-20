---
title: '방법: 지역화 된 부트스트래퍼 패키지 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
helpviewer_keywords:
- localized bootstrapper packages
- dependencies, creating localized bootstrapper packages
- prerequisites, creating localized bootstrapper packages
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1083633410c42c63f8c3e9a2ff341a2278f0b63a
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153217"
---
# <a name="how-to-create-a-localized-bootstrapper-package"></a>방법: 지역화 된 부트스트래퍼 패키지 만들기
부트스트래퍼 패키지를 만든 후 각 로캘에 대해 두 파일을 만들어 부트스트래퍼 패키지의 지역화 된 버전을 만들 수 있습니다: 소프트웨어 사용 조건 파일 (예는 *eula.rtf*) 및 패키지 매니페스트 (*package.xml*).  
  
 Visual Studio 2010에는 기본적으로 .NET Framework 4, .NET Framework 4 Client Profile, F# Runtime 2.0 및 F# Runtime 4.0용 지역화된 부트스트래퍼 패키지만 포함되어 있습니다. 3개 단계를 완료하면 다른 부트스트래퍼용 지역화된 패키지를 만들 수 있습니다.  
  
1.  로캘 이름을 따서 명명 된 폴더를 만듭니다 *\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\\<BootstrapperPackageName >* 합니다.  
  
2.  부트스트래퍼 패키지용 소프트웨어 사용 약관이 포함된 파일을 만들어 새 폴더에 저장합니다.  
  
3.  명명 된 패키지 매니페스트를 만듭니다 *package.xml*, 문자열과 문화권을 업데이트 하 고 새 폴더에 파일을 저장 합니다. 대상 언어에서의 Visual Studio 부트스트래퍼를 이미 만든 경우 Visual Studio를 복사할 수 있습니다 *package.xml* 파일을이 단계에서 수정 합니다.  
  
> [!NOTE]
>  설치 프로젝트를 응용 프로그램을 배포를 사용 하는 경우 변경 하 여 응용 프로그램을 지역화할 수 있습니다 합니다 **지역화** 속성입니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-localized-bootstrapper-package"></a>지역화된 부트스트래퍼 패키지를 만들려면  
  
1.  로캘 이름과 같은 이름을 지정하여 폴더를 만듭니다.  
  
     32 비트 컴퓨터에서 폴더를 만듭니다는 *\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\\<BootstrapperPackageName >\\*  폴더입니다.  
  
     64 비트 컴퓨터에서 폴더를 만듭니다는 *\Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\\<BootstrapperPackageName >\\*  폴더입니다.  
  
     아래 테이블에는 로캘과 일치하도록 이름을 지정하는 데 사용할 수 있는 폴더 이름이 나와 있습니다.  
  
    |로캘|폴더 이름|  
    |------------|-----------------|  
    |중국어(간체)|zh-Hans|  
    |중국어(번체)|zh-Hant|  
    |체코어|cs|  
    |독일어|de|  
    |영어|en|  
    |스페인어|es|  
    |프랑스어|fr|  
    |이탈리아어|it|  
    |한국어|ko|  
    |일본어|ja|  
    |폴란드어|pl|  
    |포르투갈어(브라질)|pt-BR|  
    |러시아어|ru|  
    |터키어|tr|  
  
2.  부트스트래퍼 패키지용 소프트웨어 사용 약관이 포함된 파일을 만들어 새 폴더에 저장합니다.  
  
3.  명명 된 패키지 매니페스트를 만듭니다 *package.xml* 새 폴더에 넣습니다. 자세한 내용은 [방법: 패키지 매니페스트 만들기](../deployment/how-to-create-a-package-manifest.md)합니다.  
  
4.  문자열이 로캘에 맞는 언어로 설정되도록 패키지 매니페스트의 `<Strings>` 섹션을 업데이트합니다.  
  
5.  폴더 이름과 일치하도록 `<String Name="Culture">` 값을 변경합니다.  
  
6.  저장 된 *package.xml* 파일입니다.  
  
### <a name="to-create-a-bootstrapper-package-for-net-framework-35-service-pack-1-localized-in-french"></a>프랑스어로 지역화된 .NET Framework 3.5 서비스 팩 1용 부트스트래퍼 패키지를 만들려면  
  
1.  라는 폴더를 만듭니다 *fr*합니다. 폴더 이름은 로캘 이름과 일치해야 합니다.  
  
     32 비트 컴퓨터에서 폴더를 만듭니다는 *\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\\*  폴더입니다.  
  
     64 비트 컴퓨터에서 폴더를 만듭니다는 *\Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\\*  폴더입니다.  
  
2.  지역화 된 버전의 소프트웨어 사용 조건에 배치 합니다 *fr* 폴더입니다.  
  
3.  복사 합니다 *\Program 파일 (x86) sdks\windows\v7.0a\bootstrapper\packages\dotnetfx35sp1\en\package.xml* 파일을 합니다 *fr* 폴더 및 XML 디자이너에서 파일을 엽니다.  
  
4.  오류 문자열이 프랑스어로 표시되도록 패키지 매니페스트의 `<Strings>` 섹션을 업데이트합니다.  
  
5.  변경 된 `<String Name="Culture">` 값을 *fr*합니다.  
  
6.  저장 된 *package.xml* 파일입니다.  
  
## <a name="see-also"></a>참고자료  
 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)   
 [응용 프로그램 배포 필수 구성 요소](../deployment/application-deployment-prerequisites.md)   
 [방법: 패키지 매니페스트 만들기](../deployment/how-to-create-a-package-manifest.md)