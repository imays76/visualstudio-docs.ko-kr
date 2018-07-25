---
title: ClickOnce 응용 프로그램 업데이트를 수행 하는 방법 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- updates, ClickOnce
- ClickOnce deployment, updates
- deploying applications [ClickOnce], application updates
ms.assetid: d54313c2-cf0c-420d-b151-99953a95f0bb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1f5d9b67633ffa2b14f780b9588f526372a4f5d
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39152521"
---
# <a name="how-clickonce-performs-application-updates"></a>ClickOnce 응용 프로그램 업데이트를 수행 하는 방법
ClickOnce 응용 프로그램의 배포 매니페스트에 지정 된 파일 버전 정보를 사용 하 여 응용 프로그램의 파일을 업데이트할 것인지를 결정 합니다. ClickOnce 라는 기술을 사용 하 여 업데이트가 시작 된 후 *파일을 패치* 응용 프로그램 파일의 중복 다운로드를 방지 합니다.  
  
## <a name="file-patching"></a>파일 패치  
 응용 프로그램을 업데이트할 때 ClickOnce 다운로드 하지 않습니다 응용 프로그램의 새 버전에 대 한 파일의 모든 파일 변경 되지 않은 경우. 대신, 새 버전에 대 한 매니페스트의 서명에 대 한 현재 응용 프로그램에 대 한 응용 프로그램 매니페스트에 지정 된 파일의 해시 서명을 비교 합니다. 파일의 서명이 다를 경우 ClickOnce는 새 버전을 다운로드 합니다. 서명이 일치 파일 변경 되지 않은 경우 버전 간에 다음입니다. 이 경우 ClickOnce 기존 파일을 복사 하 고 사용 하 여 응용 프로그램의 새 버전. 이 방법은 하나 이상의 파일이 변경 된 경우에 전체 응용 프로그램을 다시 다운로드할 필요가 ClickOnce를 방지 합니다.  
  
 패치 파일 에서도 작동 다운로드 되는 어셈블리에 대 한 사용 하 여 요청을 <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> 및 <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroupAsync%2A> 메서드.  
  
 응용 프로그램을 컴파일하려면 Visual Studio를 사용 하는 경우 전체 프로젝트를 다시 빌드할 때마다 모든 파일에 대 한 새 해시 서명을 생성 됩니다. 이 경우 소수의 어셈블리만 바꾸었을 수 있지만 모든 어셈블리를 클라이언트에 다운로드 됩니다.  
  
 파일이 패치 데이터로 표시 되 고 데이터 디렉터리에 저장 되는 파일에 대 한 작동 하지 않습니다. 이러한 파일의 해시 서명을 관계 없이 항상 다운로드 됩니다. 데이터 디렉터리에 대 한 자세한 내용은 참조 하세요. [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)합니다.  
  
## <a name="see-also"></a>참고자료  
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)   
 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)