---
title: 관리 코드 디버깅 | Microsoft Docs
description: C# 또는 Visual Studio 디버거를 사용 하 여 Visual Basic 디버그
ms.custom: mvc
ms.date: 03/18/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2ba06156a8fa44a61b489deba6104673e8fb08ce
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39637525"
---
# <a name="quickstart-debug-with-managed-code-using-the-visual-studio-debugger"></a>빠른 시작: Visual Studio 디버거를 사용 하 여 관리 되는 코드를 사용 하 여 디버그

Visual Studio 디버거에서 앱을 디버깅 하는 데 여러 가지 강력한 기능을 제공 합니다. 이 항목에는 기본 기능 중 일부에 대해 알아보는 빠른 방법을 제공합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기 

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택합니다.

2. 아래 **Visual C#** 또는 **Visual Basic**, 선택 **.NET Core**를 선택한 다음 가운데 창에서 **콘솔 앱 (.NET Core)** 합니다.

     **콘솔 앱(.NET Core)** 템플릿 프로젝트가 표시되지 않으면 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다. Visual Studio 설치 관리자가 시작됩니다. 선택 합니다 **.NET 데스크톱 개발** 하 고 **.NET Core** 워크 로드를 선택한 **수정**합니다.

3. 같은 이름을 입력 **MyDbgApp** 누릅니다 **확인**합니다.

    Visual Studio가 프로젝트를 만듭니다.

4. *Program.cs* 하거나 *Module1.vb*, 예제 코드

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
        }
    }
    ```

    ```vb
    Module Module1
        Sub Main()
        End Sub
    End Module
    ```

    이 코드로 바꿉니다.

    ```csharp
    class Program
    {
        private static void doWork()
        {
            LinkedList<int> c1 = new LinkedList<int>();

            c1.AddLast(10);
            c1.AddLast(20);

            LinkedList<int> c2 = new LinkedList<int>(c1);
            int i = c2.First.Value;
            int j = c2.First.Value;
            Console.Write("The first element is ");
            Console.Write(i);
            Console.Write("\n");
            Console.Write("The second element is ");
            Console.Write(j);
            Console.Write("\n");

        }

        static int Main()
        {
            // using namespace std;
            doWork();
            return 0;

        }
    }
    ```

    ```vb
    Imports System.Collections.Generic

    Namespace MyDbgApp
        Class Program
            Private Shared Sub doWork()
                Dim c1 As New LinkedList(Of Integer)()

                c1.AddLast(10)
                c1.AddLast(20)

                Dim c2 As New LinkedList(Of Integer)(c1)
                Dim i As Integer = c2.First.Value
                Dim j As Integer = c2.First.Value
                Console.Write("The first element is ")
                Console.Write(i)
                Console.Write(vbLf)
                Console.Write("The second element is ")
                Console.Write(j)
                Console.Write(vbLf)

            End Sub

            Public Shared Function Main() As Integer
                ' using namespace std;
                doWork()
                Return 0

            End Function
        End Class
    End Namespace
    ```

    > [!NOTE]
    > Visual Basic에서는 시작 개체가 `Sub Main`으로 설정되었는지 확인합니다(**속성 > 응용 프로그램 > 시작 개체**).

## <a name="set-a-breakpoint"></a>중단점 설정

A *중단점* 살펴보겠습니다 변수의 값 또는 메모리 또는 코드 분기의 실행 시작 여부의 동작을 수행할 수 있도록 Visual Studio 프로그램 실행 일시 중지 해야 할지 여부를 나타내는 표식 코드 됩니다. 디버깅의 가장 기본적인 기능입니다.

1. 중단점을 설정 하려면 왼쪽의 여백을 클릭 합니다 `doWork` 함수 호출 (누릅니다 코드 줄을 선택 하거나 **F9**).

    ![중단점을 설정](../debugger/media/dbg-qs-set-breakpoint-csharp.png "중단점 설정")

2. 이제 키를 눌러 **F5** (선택 하거나 **디버그 > 디버깅 시작**).

    ![중단점을 적중](../debugger/media/dbg-qs-hit-breakpoint-csharp.png "중단점 적중")

    중단점을 설정한 디버거가 일시 중지 합니다. 디버거 및 앱 실행 일시 중지 된 문에 노란색 화살표로 표시 됩니다. 한 줄으로는 `doWork` 함수 호출에서 아직 실행 되지 않았습니다.

    > [!TIP]
    > 루프 또는 재귀에 중단점이 있는 또는 자주를 단계별로 실행 하는 많은 중단점을 설정한 경우 사용 하는 경우는 [조건부 중단점](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) 특정 조건이 충족 될 경우에 코드가 일시 중단 되도록 해야 합니다. 조건부 중단점을 시간을 절약할 수 있습니다도 쉽게 재현 하기 어려운 문제를 디버깅 합니다.

## <a name="navigate-code"></a>코드 탐색

디버거를 계속 하도록 지시 하려면 명령입니다. Visual Studio 2017의 새로운 유용한 코드 탐색 명령을 보여 줍니다.

중단점에서 일시 중지 하는 동안 문을 마우스로 `c1.AddLast(20)` 녹색 될 때까지 **실행 하려면 클릭** 단추 ![실행 하려면 클릭](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 나타나고 누릅니다 합니다 **실행 하려면 클릭** 단추입니다.

![실행 하려면 클릭](../debugger/media/dbg-qs-run-to-click-csharp.png "실행 하려면 클릭")

앱 실행을 계속 호출 `doWork`, 단추를 클릭 하면 코드 줄에서 일시 중지 합니다.

하는 데 사용 되는 일반적인 키보드 명령을 포함 하는 코드를 단계별로 **F10** 하 고 **F11**합니다. 더 자세한 지침은 합니다 [초보자 가이드](../debugger/getting-started-with-the-debugger.md)합니다.

## <a name="inspect-variables-in-a-datatip"></a>Datatip에서 변수 검사

1. (노란색 실행 포인터에 의해 표시 됨) 하는 코드의 현재 줄에서 마우스로 `c1` datatip을 표시 하려면 마우스를 사용 하 여 개체입니다.

    ![Datatip 보기](../debugger/media/dbg-qs-data-tip-csharp.png "datatip 보기")

    Datatip의 현재 값을 보여 줍니다.는 `c1` 변수 및 해당 속성을 검사할 수 있습니다. 디버깅을 하지 않을 값을 표시 하는 경우 있을 버그 이전 또는 호출 줄의 코드만으로. 

2. 확장의 현재 속성 값을 확인 하려면 datatip을 `c1` 개체입니다.

3. 값이 표시를 계속할 수 있도록 datatip을 고정 하려면 `c1` 코드를 실행 하는 동안 작은 고정 아이콘을 클릭 합니다. (고정 된 datatip을 편리한 위치에 이동할 수 있습니다.)

## <a name="edit-code-and-continue-debugging"></a>코드를 편집하며 디버그 계속하기

디버깅 세션 중 코드에서 테스트 하려는 변경을 식별 하는 경우에 너무 수행할 수 있습니다.

1. 두 번째 인스턴스를 클릭 `c2.First.Value` 변경할 `c2.First.Value` 에 `c2.Last.Value`입니다.

2. 키를 눌러 **F10** (또는 **디버그 > 프로시저 단위 실행**) 디버거로 이동할 편집한 코드를 실행 하는 여러 번입니다.

    ![편집 하며 계속 하기](../debugger/media/dbg-qs-edit-and-continue-csharp.gif "편집 하며 계속 하기")

    **F10** 시간만 단계에 디버거를 한 명령문 (건너뛰기 코드가 계속 실행)를 단계별로 실행 하는 대신 함수를 통해 이동 합니다.

기능 제한 편집 하며 계속 하기 사용에 대 한 자세한 내용은 참조 [편집 하며 계속 하기](../debugger/edit-and-continue.md)합니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 디버거를 시작 하면 코드를 단계별로 실행 하 여 변수를 검사 하는 방법을 알아보았습니다. 자세한 정보에 대 한 링크와 함께 디버거 기능에 간략히 살펴보고 가져오려는 수 있습니다.

> [!div class="nextstepaction"]
> [디버거 기능 둘러보기](../debugger/debugger-feature-tour.md)
