---
title: IntelliTrace 사용 하 여 이벤트를 보려면 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e1c9c91a-0009-4c4e-9b4f-c9ab3a6022a7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 86410567a194753db2001fbd5fba870bb89d7930
ms.sourcegitcommit: 01185dadd2fa1f9a040d2a366869f1a5e1d18e0f
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54227995"
---
# <a name="view-events-with-intellitrace-in-visual-studio-enterprise-c-visual-basic"></a>Visual Studio Enterprise에서 IntelliTrace 사용 하 여 이벤트를 확인 (C#, Visual Basic)

IntelliTrace를 사용하여 특정 이벤트 또는 이벤트 범주나 이벤트 외에 개별 함수 호출에 대한 정보를 수집할 수 있습니다. 다음 절차에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
Visual Studio Enterprise 버전(Professional 또는 Community 버전 아님)에서 IntelliTrace를 사용할 수 있습니다.  
  
##  <a name="GettingStarted"></a> IntelliTrace를 구성 합니다.  

 IntelliTrace 이벤트로만 디버그를 시도할 수 있습니다. IntelliTrace 이벤트에는 디버거 이벤트, 예외, .NET Framework 이벤트 및 기타 시스템 이벤트가 있습니다. 특정 이벤트를 켜거나 꺼서 디버깅을 시작하기 전에 IntelliTrace에서 기록하는 이벤트를 제어할 수 있습니다. 자세한 내용은 [IntelliTrace 기능](../debugger/intellitrace-features.md)합니다.  
  
 - 파일 액세스에 대한 IntelliTrace 이벤트 켜기 **도구 / 옵션 / IntelliTrace / IntelliTrace 이벤트** 페이지로 이동하고 **파일** 범주를 확장합니다. **파일** 이벤트 범주를 확인합니다. 이렇게 하면 모든 파일 이벤트(액세스, 닫기, 삭제)가 확인됩니다.

## <a name="create-your-app"></a>앱 만들기
  
1.  C# 콘솔 애플리케이션을 만듭니다. Program.cs 파일에서 다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using System.IO;  
    ```  
  
2.  Main 메서드에서 <xref:System.IO.FileStream> 을 만들고 여기에서 읽고 닫고 파일을 삭제합니다. 다른 줄을 추가하여 중단점을 설정할 위치 지정합니다.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        FileStream fs = File.Create("WordSearchInputs.txt");  
        fs.ReadByte();  
        fs.Close();  
        File.Delete("WordSearchInputs.txt");  
  
        Console.WriteLine("done");  
    }  
    ```  
  
3.  `Console.WriteLine("done");`에서 중단점 설정  

## <a name="start-debugging-and-view-intellitrace-events"></a>디버깅을 시작 하 고 IntelliTrace 이벤트 보기
  
1.  일반적인 방법으로 디버깅을 시작합니다. ( **F5** 키를 누르거나 **디버그 / 디버깅 시작**을 클릭합니다.)  
  
    > [!TIP]
    >  **로컬** 및 **자동** 창에서 값을 보고 기록하기 위해 디버그하는 동안 해당 창은 열어 두세요.  
  
2.  중단점에서 실행이 중지됩니다. **진단 도구** 창이 표시되지 않으면, **디버그 / Windows / IntelliTrace 이벤트**를 클릭합니다.  
  
     **진단 도구** 창에서 **이벤트** 탭을 찾으세요( **이벤트**, **메모리 사용량**및 **CPU 사용량**, 이렇게 3개의 탭이 표시되어야 함). **이벤트** 탭에는 디버거 실행이 중단되기 전에 마지막 이벤트로 끝나는 시간 순 이벤트 목록이 표시됩니다. **WordSearchInputs.txt 액세스**라는 이벤트가 표시되어야 합니다.  
  
     다음 스크린샷은 Visual Studio 2015 업데이트 1에서 시작됩니다.  
  
     ![IntelliTrace&#45;Update1](../debugger/media/intellitrace-update1.png "IntelliTrace-업데이트 1")  
  
3.  이벤트를 선택하여 해당 세부 정보를 확장합니다.  
  
     다음 스크린샷은 Visual Studio 2015 업데이트 1에서 시작됩니다.  
  
     ![IntelliTraceUpdate1&#45;SingleEvent](../debugger/media/intellitraceupdate1-singleevent.png "IntelliTraceUpdate1-SingleEvent")  
  
     경로 이름 링크를 선택하여 파일을 열 수 있습니다. 전체 경로 이름을 사용할 수 없는 경우에는 **파일 열기** 대화 상자가 나타납니다.  
  
     **기록 디버깅 활성화**를 클릭하면 디버거의 컨텍스트가 선택한 이벤트를 수집한 시간으로 설정되고 **호출 스택**, **로컬** 및 기타 참여 디버거 창에 기록 데이터가 표시됩니다. 소스 코드를 사용할 수 있는 경우 Visual Studio가 소스 창에서 포인터를 해당 코드로 이동하여 검사할 수 있게 합니다.  
  
     다음 스크린샷은 Visual Studio 2015 업데이트 1에서 시작됩니다.  
  
     ![HistoricalDebugging&#45;Update1](../debugger/media/historicaldebugging-update1.png "HistoricalDebugging-업데이트 1")  
  
4.  버그를 찾지 못한 경우 버그를 발생시키는 기타 이벤트를 검사합니다. 함수 호출을 단계별로 실행할 수 있도록 IntelliTrace에서 호출 정보를 기록하게 할 수도 있습니다. 
  
## <a name="next-steps"></a>다음 단계

기록 디버깅 IntelliTrace의 고급 기능 중 일부를 사용할 수 있습니다.

 - 스냅숏을 보려면을 참조 하세요. [IntelliTrace를 사용 하 여 이전 앱 상태를 검사 합니다.](../debugger/view-historical-application-state.md)
 - 변수를 검사 하 고 코드를 탐색 하는 방법에 알아보려면 참조 [기록 디버깅을 사용 하 여 앱 검사](../debugger/historical-debugging-inspect-app.md)