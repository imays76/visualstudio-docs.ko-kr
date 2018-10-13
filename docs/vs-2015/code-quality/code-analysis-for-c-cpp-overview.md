---
title: C-c + + 개요에 대 한 코드 분석 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
caps.latest.revision: 27
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 42de573efcc44437eddf0e7d098681d05c094131
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49222042"
---
# <a name="code-analysis-for-cc-overview"></a>C/C++용 코드 분석 개요
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

C/C++ 코드 분석 도구는 C/C++ 소스 코드에서 발생할 수 있는 오류에 대한 정보를 개발자에게 제공합니다. 이 도구를 통해 보고되는 일반적인 코딩 오류에는 버퍼 오버런, 초기화되지 않은 메모리, null 포인터 역참조, 메모리 및 리소스 누수 등이 포함됩니다.  
  
## <a name="ide-integrated-development-environment-integration"></a>IDE(통합 개발 환경) 통합  
 개발자 분석 도구를 사용 하는 자연 스러운 확인에 완전히 통합 되며 내는 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] IDE. 빌드 프로세스 중 소스 코드에 대해 생성 된 모든 경고가 오류 목록에 표시 됩니다. 경고를 발생 시킨 소스 코드를 이동할 수 있습니다 및 해당 원인 및 문제 해결에 대 한 추가 정보를 볼 수 있습니다.  
  
## <a name="pragma-support"></a>#pragma 지원  
 개발자가 사용할 수는 `#pragma` 지시문 경고를 오류로 처리; 설정 또는 경고를 해제 하 고 개별 코드 줄에 대 한 경고를 표시 하지 않을 수 있습니다. 자세한 내용은 [방법: 설정 및 특정 C/c + + 경고에 대 한 코드 분석 사용 안 함](http://msdn.microsoft.com/en-us/910b8518-71f1-4b2e-b012-70647795642a)합니다.  
  
## <a name="annotation-support"></a>주석 지원  
 주석을 코드 분석의 정확성을 개선 합니다. 주석이 함수 매개 변수에서 사전 및 사후 조건에 대 한 추가 정보를 제공 및 반환 형식입니다. 자세한 내용은 참조 하세요. [방법: __analysis_assume를 사용 하 여 추가 코드 정보 지정](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)  
  
## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>체크 인 정책의 일부로 분석 도구를 실행 합니다.  
 모든 소스 코드 체크 인 특정 정책을 충족 필요할 수도 있습니다. 특히, 최신 로컬 빌드 단계로 분석을 실행 하는지 확인 하려고 합니다. 코드 분석 체크 인 정책을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [만들기 및 사용 하 여 코드 분석 체크 인 정책](../code-quality/creating-and-using-code-analysis-check-in-policies.md)  
  
## <a name="team-build-integration"></a>팀 빌드 통합  
 단계로 코드 분석 도구를 실행 하려면 빌드 시스템의 통합된 된 기능을 사용할 수는 [!INCLUDE[esprtfs](../includes/esprtfs-md.md)] 빌드 프로세스입니다. 자세한 내용은 [응용 프로그램 빌드](http://msdn.microsoft.com/library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)를 참조하세요.  
  
## <a name="command-line-support"></a>명령줄 지원  
 개발 환경 내에 전체 통합 하는 것 외에도 개발자는 다음 예와에서 같이 명령줄에서 분석 도구를 사용도 수 있습니다.:  
  
 `C:\>cl /analyze Sample.cpp`



