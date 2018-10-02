---
title: 디버깅 하는 동안 XAML 속성 검사 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 390edde4-7b8d-4c89-8d69-55106b7e6b11
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb10290e14290f59950e6b291d479de2099ac7f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47565342"
---
# <a name="inspect-xaml-properties-while-debugging"></a>디버그하는 동안 XAML 속성 검사
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [디버깅 하는 동안 검사할 XAML 속성](https://docs.microsoft.com/visualstudio/debugger/inspect-xaml-properties-while-debugging)합니다.  
  
실시간 보기를 사용 하 여 실행 중인 XAML 코드를 가져올 수 있습니다 합니다 **라이브 시각적 트리** 하며 **라이브 속성 탐색기**합니다. 이러한 도구는 실행 중인 XAML 응용 프로그램의 UI 요소에 대한 트리 뷰를 제공하고 선택한 UI 요소의 런타임 속성을 보여 줍니다.  
  
 다음 구성에서 이러한 도구를 사용할 수 있습니다.  
  
|앱 유형|운영 체제 및 도구|  
|-----------------|--------------------------------|  
|Windows Presentation Foundation(4.0 이상) 응용 프로그램|Windows 7 이상|  
|Windows 스토어 및 Windows Phone 8.1 앱|Windows 10 이상에서 사용 하 여는 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)|  
|유니버설 Windows 앱|Windows 10 이상에서 사용 하 여는 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)|  
  
## <a name="looking-at-elements-in-the-live-visual-tree"></a>라이브 시각적 트리의 요소 보기  
 목록 보기 및 단추가 있는 매우 간단한 WPF 응용 프로그램을 시작하겠습니다. 단추를 클릭할 때마다 다른 항목이 목록에 추가됩니다. 짝수 번호 항목은 회색으로 표시되고 홀수 번호 항목은 노란색으로 표시됩니다.  
  
 새 C# WPF 응용 프로그램을 만듭니다(파일 / 새로 만들기 / 프로젝트를 선택한 다음 C#을 선택하고 WPF 응용 프로그램 찾기). 이름을 **TestXAML**합니다.  
  
 다음과 같이 MainWindow.xaml을 변경합니다.  
  
```xaml  
<Window x:Class="WpfApplication1.MainWindow"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:local="clr-namespace:WpfApplication1"  
    mc:Ignorable="d"  
     Title="MainWindow" Height="350" Width="525">  
    <Grid>  
        <Button x:Name="button" Background="LightBlue" Content="Add Item" HorizontalAlignment="Left" Margin="216,206,0,0" VerticalAlignment="Top" Width="75" Click="button_Click"/>  
        <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="100" VerticalAlignment="Top" Width="100" Margin="205,80,0,0"/>  
    </Grid>  
</Window>  
```  
  
 MainWindow.xaml.cs 파일에 다음 명령 처리기를 추가합니다.  
  
```csharp  
private void button_Click(object sender, RoutedEventArgs e)  
{  
    ListBoxItem item = new ListBoxItem();  
    item.Content = "Item" + ++count;  
    if (count % 2 == 0)  
    {  
        item.Background = Brushes.LightGray;  
    }  
    else  
    {  
        item.Background = Brushes.LightYellow;  
    }  
    listBox.Items.Add(item);  
}  
```  
  
 프로젝트를 빌드하고 디버깅을 시작합니다. (빌드 구성은 릴리스가 아닌 디버그여야 합니다. 빌드 구성에 대 한 자세한 내용은 참조 하세요. [빌드 구성 이해](../ide/understanding-build-configurations.md).)  
  
 창이 표시 되 면 클릭 합니다 **항목 추가** 단추를 몇 번입니다. 다음과 같이 표시되어야 합니다.  
  
 ![앱의 주 창이](../debugger/media/livevisualtree-app.png "LiveVIsualTree 앱")  
  
 이제 열을 **라이브 시각적 트리** 창 (**디버그 / Windows / 라이브 시각적 트리**, 또는 IDE의 왼쪽을 따라 찾기). 이 창에서 볼 수 있도록 해당 도킹 위치에서 벗어나도록 끕니다 하며 **라이브 속성** 창을 나란히 합니다. 에 **라이브 시각적 트리** 창에서 확장을 **ContentPresenter** 노드. 단추와 목록 상자에 대한 노드가 있어야 합니다. 목록 상자를 확장 (차례로 합니다 **ScrollContentPresenter** 하며 **ItemsPresenter**) 목록 상자 항목을 찾으려면 합니다. 창이 다음과 같이 표시되어야 합니다.  
  
 ![라이브 시각적 트리의 Listboxitem](../debugger/media/livevisualtree-listboxitems.png "LiveVisualTree Listboxitem")  
  
 응용 프로그램 창으로 다시 이동하고 더 많은 항목을 추가합니다. 에 표시 하는 자세한 목록 상자 항목을 표시 합니다 **라이브 시각적 트리**합니다.  
  
 이제 목록 상자 항목 중 하나의 속성을 살펴보겠습니다. 첫 번째 목록 상자 항목 선택는 **라이브 시각적 트리** 클릭 합니다 **속성을 표시** 도구 모음에서 아이콘. 합니다 **라이브 속성 탐색기** 표시 되어야 합니다. 합니다 **콘텐츠** 필드는 "Item1", 및 **배경** 필드가 **#ffffffe0** (연한 노랑)입니다. 로 다시 이동 합니다 **라이브 시각적 트리** 두 번째 목록 상자 항목을 선택 합니다. **라이브 속성 탐색기** 것으로 표시 됩니다는 **콘텐츠** 필드는 "Item2", 및 **백그라운드** 필드가 **#ffd3d3d3** (밝은 회색 ).  
  
 XAML의 실제 구조에는 직접적으로 관련이 없는 많은 요소가 있습니다. 코드를 잘 모르면 트리에서 필요한 항목을 찾기가 어려울 수 있습니다. 하므로 **라이브 시각적 트리** 에 여러 가지 방법으로 응용 프로그램의 UI를 사용 하 여 검사 하려는 요소를 찾을 수 있도록 합니다.  
  
 **실행 중인 응용 프로그램에서 선택 사용**합니다. 왼쪽에 있는 단추를 선택 하면이 모드를 설정할 수 있습니다.는 **라이브 시각적 트리** 도구 모음입니다. 이 모드를 사용 하 여 응용 프로그램에서 UI 요소를 선택할 수 있습니다 및 **라이브 시각적 트리** (하며 **라이브 속성 뷰어**) 자동으로 해당 요소에 해당 하는 트리에서 노드를 표시 하도록 업데이트 및 해당 속성을 추가 합니다.  
  
 **실행 중인 응용 프로그램에 레이아웃 표시기 표시**합니다. 선택 사용 단추 바로 오른쪽에 있는 단추를 선택하면 이 모드를 사용할 수 있습니다. 때 **레이아웃 표시기 표시** 가 on으로 설정 하면 어떤 항목이 정렬 되는지, 여백을 표시 하는 사각형 뿐만 아니라 볼 수 있도록 선택한 개체의 경계를 따라 가로 및 세로 줄을 표시 하도록 응용 프로그램 창입니다. 예를 들어, 모두를 켜고 **선택을 가능 하 게** 및 **표시 레이아웃** 선택 합니다 **항목 추가** 응용 프로그램에서 텍스트 블록입니다. 에 텍스트 블록 노드가 표시 됩니다는 **라이브 시각적 트리** 및 텍스트 블록 속성이 합니다 **라이브 속성 뷰어**, 텍스트 블록의 범위에 가로 및 세로 줄 뿐만 아니라 합니다.  
  
 ![Displaylayout의 Livepropertyviewer](../debugger/media/livevisualtreelivepropertyviewer-displaylayout.png "LiveVisualTreeLivePropertyViewer DisplayLayout")  
  
 **선택 미리 보기**합니다. 라이브 시각적 트리 도구 모음의 왼쪽에서 세 번째 단추를 선택하면 이 모드를 사용할 수 있습니다. 이 모드에서는 응용 프로그램의 소스 코드에 액세스할 수 있는 경우 요소가 선언된 XAML을 보여 줍니다. 선택 **선택을 가능 하 게** 하 고 **선택 미리 보기**, 테스트 응용 프로그램에서 단추를 선택 합니다. Visual Studio에서 MainWindow.xaml 파일이 열리고 커서가 단추가 정의된 줄에 위치합니다.  
  
## <a name="using-xaml-tools-with-running-applications"></a>응용 프로그램이 실행 중인 상태에서 XAML 도구를 사용  
 소스 코드가 없는 경우 이러한 XAML 도구를 사용할 수 있습니다. 실행 중인 XAML 응용 프로그램에 연결할 때 사용할 수는 **라이브 시각적 트리** 해당 응용 프로그램의 UI 요소에서 너무 합니다. 다음은 이전에 사용한 동일한 WPF 테스트 응용 프로그램을 사용하는 예제입니다.  
  
1.  시작 합니다 **TestXaml** 릴리스 구성에서 응용 프로그램입니다. 실행 중인 프로세스에 연결할 수 없습니다는 **디버그** 구성 합니다.  
  
2.  Visual Studio의 두 번째 인스턴스를 열고 **디버그 / 프로세스에 연결**합니다. 찾을 **TestXaml.exe** 하 고 사용 가능한 프로세스 목록에서 **연결**합니다.  
  
3.  응용 프로그램이 실행되기 시작합니다.  
  
4.  Visual Studio의 두 번째 인스턴스의 경우에서 엽니다는 **라이브 시각적 트리** (**디버그 / Windows / 라이브 시각적 트리**). 표시 되어야 합니다 **TestXaml** UI 요소를 직접 응용 프로그램을 디버깅 하는 동안이 했던 대로 조작할 수 있어야 합니다.



