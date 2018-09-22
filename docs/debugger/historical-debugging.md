---
title: 기록 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a622fcb91ad40e7d0777f37ce87e9a2cb950695
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542405"
---
# <a name="historical-debugging"></a>기록 디버깅
기록 디버깅은 IntelliTrace에서 수집된 정보에 의존하는 디버깅 모드입니다. 이 디버깅을 사용하면 응용 프로그램 실행 도중 앞이나 뒤로 이동하며 상태를 검사할 수 있습니다.  
  
 Visual Studio Enterprise Edition(Professional 또는 Community Edition 아님)에서 IntelliTrace를 사용할 수 있습니다.  
  
## <a name="why-use-historical-debugging"></a>기록 디버깅 사용 하는 이유?  
 버그를 찾는 중단점을 설정하는 것은 적중하느냐 누락하느냐의 문제입니다. 코드에서 버그가 있을 것으로 의심되는 위치 가까이에 중단점을 설정하면 디버거에서 응용 프로그램을 실행할 때 중단점이 적중될 것으로 기대할 수 있고, 이에 따라 실행이 중단된 위치가 버그 소스를 노출할 수 있습니다. 그렇지 않은 경우 다른 위치에 코드에서 중단점을 설정 하 고 문제를 찾을 때까지 테스트 단계를 계속 해 서 실행 하 고 디버거를 다시 실행 해야 합니다.  
  
 ![중단점을 설정](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 IntelliTrace와 기록 디버깅를 사용 하 여 응용 프로그램에서 돌아다닐 중단점을 설정 하려면 디버깅을 다시 시작 하지 않고도 해당 상태 (호출 스택 및 지역 변수) 검사를 하 고 테스트 단계를 반복할 수 있습니다. 이렇게 하면 특히 버그가 테스트 시나리오의 깊은 수준에 있어서 실행하는 데 오래 걸리는 경우 많은 시간을 절약할 수 있습니다.  
  
## <a name="how-do-i-start-using-historical-debugging"></a>기록 디버깅을 사용 하 여 시작 하려면 어떻게 해야 하나요?  
 IntelliTrace는 기본적으로 설정되어 있습니다. 이벤트 및 함수 호출 관심 하 고 전체 응용 프로그램 상태의 스냅숏 보기 것인지 결정 하면 됩니다. 에 대 한 확인 하려는 항목을 정의 하는 방법에 대 한 자세한 내용은 참조 하세요. [IntelliTrace 기능](../debugger/intellitrace-features.md)합니다.  

 - 기록 디버깅을 사용 하는 스냅숏을 보려면 참조 [IntelliTrace를 사용 하 여 이전 앱 상태를 검사 합니다.](../debugger/view-historical-application-state.md)
 - 변수를 검사 하 고 코드를 탐색 하는 방법에 알아보려면 참조 [기록 디버깅을 사용 하 여 앱 검사](../debugger/historical-debugging-inspect-app.md)
 - IntelliTrace 이벤트를 사용 하 여 디버깅 하는 방법에 대 한 자세한 내용은 참조 하세요 [연습: IntelliTrace를 사용 하 여](../debugger/walkthrough-using-intellitrace.md)입니다.