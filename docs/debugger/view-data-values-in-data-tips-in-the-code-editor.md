---
title: 코드 편집기에서 DataTips의 데이터 값 보기 | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], DataTips
- DataTips tool
ms.assetid: ffa7bd18-439b-4685-a9b3-c7884b5de41f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: afb318c8aa327345b3cd76ee16b718db1e0386aa
ms.sourcegitcommit: 331dbb12e11fcd7f5d15fab05f3c861e48126e43
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51826761"
---
# <a name="view-data-values-in-datatips-in-the-code-editor"></a>코드 편집기에서 DataTips의 데이터 값 보기
DataTips를 통해 디버깅하는 동안 프로그램의 변수에 대한 정보를 손쉽게 볼 수 있습니다. DataTips는 중단 모드에서 현재 실행 범위 내의 변수에 대해서만 작동합니다. 읽을 하려는 처음 코드를 디버그 하려는 경우 [보다 효과적으로 작성할 C# Visual Studio를 사용 하 여 코드](../debugger/write-better-code-with-visual-studio.md) 하 고 [초보자를 위한 디버깅](../debugger/debugging-absolute-beginners.md) 이 문서를 진행 하기 전에 합니다.
  
### <a name="to-display-a-datatip"></a>DataTip을 표시 하려면  
  
1. 중단점을 설정 하 고 디버깅을 시작 (키를 눌러 **F5**).

2. 디버거에서 일시 중지 된 경우 현재 범위에 있는 변수 위에 마우스 포인터를 놓습니다.
  
     DataTips가 나타납니다.
  
3.  마우스 포인터를 제거하면 DataTip이 사라집니다. 파일을 열린 상태로 유지 됩니다 있도록 DataTip을 고정 하려면 클릭 합니다 **소스에 고정** 아이콘 또는 변수를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **소스에 고정**합니다.

    ![고정 데이터 팁](../debugger/media/dbg-tips-data-tips-pinned.png "PinningDataTip")

    > [!NOTE]
    > DataTip은 커서가 가리키고 있는 컨텍스트가 아니라 실행이 일시 중단된 컨텍스트에서 항상 평가됩니다. 현재 컨텍스트에 있는 변수와 이름이 같은 또 다른 함수의 변수를 가리키는 경우 다른 함수의 변수 값이 현재 컨텍스트의 변수 값으로 표시됩니다.
  
### <a name="to-unpin-a-datatip-and-make-it-float"></a>DataTip의 고정을 해제하고 다른 위치에 배치하려면  
  
-   고정 된 DataTip을 클릭 합니다 **소스에서 고정 해제** 아이콘입니다.  
  
     고정 아이콘이 고정 해제된 위치로 변경됩니다. 이제 DataTip이 열린 창 위에 배치됩니다. 부동 DataTip은 디버깅 세션이 종료될 때 닫힙니다.  
  
### <a name="to-repin-a-floating-datatip"></a>부동 DataTip을 다시 고정하려면  
  
-   DataTip에서 고정 아이콘을 클릭합니다.  
  
     고정 아이콘이 고정된 위치로 바뀝니다. DataTip이 소스 창 밖에 있으면 고정 아이콘을 사용할 수 없으며 DataTip을 고정할 수 없습니다.  
  
### <a name="to-close-a-datatip"></a>DataTip을 닫으려면  
  
-   마우스 포인터를 DataTip 위에 놓고 클릭 합니다는 **닫기** 아이콘입니다.  
  
### <a name="to-close-all-datatips"></a>모든 DataTips를 닫으려면  
  
-   에 **디버그** 메뉴에서 클릭 **모든 DataTips 지우기**합니다.  
  
### <a name="to-close-all-datatips-for-a-specific-file"></a>특정 파일에 대한 모든 DataTips를 닫으려면  
  
-   에 **디버그** 메뉴에서 클릭 **지우기 모든에 고정 된 DataTips** *파일*합니다.  
  
## <a name="expand-and-edit-information"></a>확장 하 고 정보 편집  
 DataTips를 사용하면 배열, 구조체 또는 개체를 확장하여 해당 멤버를 볼 수 있습니다. DataTips에서 변수 값을 편집할 수도 있습니다.  
  
#### <a name="to-expand-a-variable-to-see-its-elements"></a>변수를 확장하여 해당 요소를 보려면  
  
-   DataTip에서 위에 마우스 포인터를 놓고 합니다 **+** 변수 이름 앞에 오는 로그인 합니다.  
  
    변수가 확장되어 해당 요소가 트리 형태로 표시됩니다.

    ![데이터 팁을 보려면](../debugger/media/dbg-tour-data-tips.gif "데이터 팁 보기")
  
    변수가 확장되면 키보드의 화살표 키를 사용하여 위아래로 이동할 수 있습니다. 또는 마우스를 사용할 수 있습니다.  
  
#### <a name="to-edit-the-value-of-a-variable-using-a-datatip"></a>DataTip을 사용하여 변수 값을 편집하려면  
  
1.  DataTip에서 값을 클릭합니다. 읽기 전용 값에는 사용할 수 없습니다.  
  
2.  새 값을 입력하고 Enter 키를 누릅니다.  
  
## <a name="making-a-datatip-transparent"></a>DataTips 투명하게 만들기  
 DataTip 뒤에 있는 코드를 보려면 DataTip을 임시로 투명하게 만듭니다. 고정 또는 부동 DataTips에는 적용되지 않습니다.  
  
#### <a name="to-make-a-datatip-transparent"></a>DataTips를 투명하게 만들려면  
  
-   DataTip에서 Ctrl 키를 누릅니다.  
  
     Ctrl 키를 누르고 있는 동안에는 DataTip이 투명한 상태로 유지됩니다.  
  
## <a name="visualize-complex-data-types"></a>복잡 한 데이터 형식을 시각화합니다  
 하나 이상의 DataTip에서 변수 이름 옆에 돋보기 모양 아이콘이 나타나면 [시각화 도우미](../debugger/create-custom-visualizers-of-data.md)와 같은 [문자열 시각화 도우미가](../debugger/string-visualizer-dialog-box.md), 해당 데이터 형식의 변수에 사용할 수 있습니다. 시각화 도우미를 사용하면 정보를 더 의미 있는 방식(대개 그래픽 방식)으로 표시할 수 있습니다.
  
#### <a name="to-view-the-contents-of-a-variable-using-a-visualizer"></a>시각화 도우미를 사용하여 변수의 내용을 보려면  
  
-   돋보기 아이콘을 클릭 ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "시각화 아이콘") 데이터 형식에 대 한 기본 시각화 도우미를 선택 합니다.  
  
     또는  
  
     시각화 도우미 옆의 팝업 화살표를 클릭하고 시각화 도우미 목록에서 데이터 형식에 적절한 시각화 도우미를 선택합니다.  
  
     시각화 도우미가 정보를 표시합니다.  
  
## <a name="add-information-to-a-watch-window"></a>조사식 창에 정보를 추가 합니다.  
 목록 뷰에서 변수 조사를 계속 하려는 경우에 변수를 추가할 수 있습니다 합니다 **조사식** DataTip에서 창입니다.  
  
#### <a name="to-add-a-variable-to-the-watch-window"></a>조사식 창에 변수를 추가하려면  
  
-   DataTip을 마우스 오른쪽 단추로 누른 **조사식 추가**합니다.  
  
     추가할 변수를 **조사식** 창. 여러를 지 원하는 버전을 사용 하는 경우 **조사식** windows 변수의 추가할 **조사식 1입니다.**  
  
## <a name="import-and-export-datatips"></a>DataTips 내보내기 및 가져오기  
 DataTips를 XML 파일로 내보내서 동료와 공유하거나 텍스트 편집기를 사용하여 편집할 수 있습니다.  
  
#### <a name="to-export-datatips"></a>DataTips를 내보내려면  
  
1.  디버그 메뉴에서 클릭 **DataTips 내보내기**합니다.  
  
     합니다 **DataTips 내보내기** 대화 상자가 나타납니다.  
  
2.  표준 파일 기술을 사용 하 여 파일의 이름을 입력 XML 파일을 저장 하려는 위치로 이동 합니다 **파일 이름** 상자를 선택한 다음 클릭 **확인**합니다.  
  
#### <a name="to-import-datatips"></a>DataTips를 가져오려면  
  
1.  디버그 메뉴에서 클릭 **DataTips 가져오기**합니다.  
  
     합니다 **DataTips 가져오기** 대화 상자가 나타납니다.  
  
2.  대화 상자를 사용 하 여 열고 클릭 하려는 XML 파일을 찾습니다 **확인**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [새로운를 디버그 하시 나요?](../debugger/what-is-debugging.md)  
 [보다 효과적으로 작성할 C# Visual Studio를 사용 하는 코드](../debugger/write-better-code-with-visual-studio.md)  
 [디버깅 소개](../debugger/debugger-feature-tour.md) [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [조사식 및 간략 한 조사식 Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Create Custom Visualizers of Data](../debugger/create-custom-visualizers-of-data.md)(데이터의 사용자 지정 시각화 도우미 만들기)   