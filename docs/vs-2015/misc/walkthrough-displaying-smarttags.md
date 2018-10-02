---
title: '연습: 스마트 태그 표시 | Microsoft Docs'
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
- editors [Visual Studio SDK], new - smart tags
ms.assetid: 10bb4f69-b259-41f0-b91a-69b04385d9a5
caps.latest.revision: 31
manager: douge
ms.openlocfilehash: 15e02986012f186ce4bcb2fdcd6914396b2b597e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554328"
---
# <a name="walkthrough-displaying-smarttags"></a>연습: 스마트 태그 표시
스마트 태그는 전구로 대체되었습니다. 참조 [연습: Displaying Light Bulb Suggestions](../extensibility/walkthrough-displaying-light-bulb-suggestions.md)합니다.  
  
 스마트 태그는 일련의 동작을 표시하도록 확장되는 텍스트 태그입니다. 예를 들어 Visual Basic 또는 Visual C# 프로젝트에서 변수 이름과 같은 식별자의 이름을 바꾸면 단어 아래에 빨간색 선이 나타납니다. 밑줄 위로 포인터를 이동하면 포인터 근처에 단추가 표시됩니다. 단추를 클릭하면 제안 동작이 표시됩니다(예: **IsRead의 이름을 IsReady로 바꾸기**). 동작을 클릭하면 프로젝트에서 **IsRead** 에 대한 모든 참조의 이름이 **IsReady**로 바뀝니다.  
  
 스마트 태그는 편집기에서 IntelliSense 구현의 일부를 서브클래싱하 여 스마트 태그를 구현할 수 있습니다 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag>, 한 다음 합니다 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> 인터페이스 및 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider> 인터페이스입니다.  
  
> [!NOTE]
>  비슷한 방식으로 다른 종류의 태그를 구현할 수 있습니다.  
  
 다음 연습에서는 현재 단어에 표시되고 두 개의 제안 동작( **대문자로 변환** 및 **를 소문자로 변환**)이 있는 스마트 태그를 만드는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>MEF(Managed Extensibility Framework) 프로젝트 만들기  
  
#### <a name="to-create-a-mef-project"></a>MEF 프로젝트를 만들려면  
  
1.  편집기 분류자 프로젝트를 만듭니다. 솔루션의 이름을 `SmartTagTest`로 지정합니다.  
  
2.  VSIX 매니페스트 편집기에서 source.extension.vsixmanifest 파일을 엽니다.  
  
3.  **자산** 섹션에 `Microsoft.VisualStudio.MefComponent` 형식이 포함되어 있고, **소스** 가 `A project in current solution`으로 설정되었으며, **프로젝트** 가 SmartTagTest.dll로 설정되었는지 확인합니다.  
  
4.  source.extension.vsixmanifest를 저장하고 닫습니다.  
  
5.  프로젝트에 대한 다음 참조를 추가하고 **CopyLocal** 을 `false`로 설정합니다.  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
6.  기존 클래스 파일을 삭제합니다.  
  
## <a name="implementing-a-tagger-for-smart-tags"></a>스마트 태그에 대한 태거 구현  
  
#### <a name="to-implement-a-tagger-for-smart-tags"></a>스마트 태그에 대한 태거를 구현하려면  
  
1.  클래스 파일을 추가하고 이름을 `TestSmartTag`로 지정합니다.  
  
2.  다음 가져오기를 추가합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#1](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#1)]
     [!code-vb[VSSDKSmartTagTest#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#1)]  
  
3.  라는 클래스를 추가 `TestSmartTag` 에서 상속 되는 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag>합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#2](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#2)]
     [!code-vb[VSSDKSmartTagTest#2](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#2)]  
  
4.  사용 하 여 기본 생성자를 호출 하는이 클래스의 생성자를 추가 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType> 의 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType>, 단어의 첫 문자 아래에 나타나도록 하려면 파란색 선 발생 합니다. (사용 하는 경우 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType>, 단어의 마지막 문자 아래에 빨간색 선이 표시 됩니다.)  
  
     [!code-csharp[VSSDKSmartTagTest#3](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#3)]
     [!code-vb[VSSDKSmartTagTest#3](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#3)]  
  
5.  라는 클래스를 추가 `TestSmartTagger` 에서 상속 되는 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> 형식의 `TestSmartTag`, 구현 및 <xref:System.IDisposable>합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#4](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#4)]
     [!code-vb[VSSDKSmartTagTest#4](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#4)]  
  
6.  태거 클래스에 다음과 같은 전용 필드를 추가합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#5](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#5)]
     [!code-vb[VSSDKSmartTagTest#5](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#5)]  
  
7.  전용 필드를 설정 및 구독 하는 생성자를 추가 합니다 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 이벤트입니다.  
  
     [!code-csharp[VSSDKSmartTagTest#6](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#6)]
     [!code-vb[VSSDKSmartTagTest#6](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#6)]  
  
8.  구현 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> 현재 단어에 대 한 태그가 만들어지도록 합니다. 이 메서드는 나중에 설명하는 private 메서드 `GetSmartTagActions` 도 호출합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#7](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#7)]
     [!code-vb[VSSDKSmartTagTest#7](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#7)]  
  
9. `GetSmartTagActions` 메서드를 추가하여 스마트 태그 동작을 설정합니다. 동작 자체는 이후 단계에서 구현됩니다.  
  
     [!code-csharp[VSSDKSmartTagTest#8](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#8)]
     [!code-vb[VSSDKSmartTagTest#8](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#8)]  
  
10. `SmartTagsChanged` 이벤트를 선언합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#9](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#9)]
     [!code-vb[VSSDKSmartTagTest#9](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#9)]  
  
11. 구현 합니다 `OnLayoutChanged` 발생 시키는 이벤트 처리기는 `TagsChanged` 이벤트, <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> 호출할 합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#10](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#10)]
     [!code-vb[VSSDKSmartTagTest#10](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#10)]  
  
12. 구현 된 <xref:System.IDisposable.Dispose%2A> 에서 구독 취소 메서드는 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 이벤트입니다.  
  
     [!code-csharp[VSSDKSmartTagTest#11](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#11)]
     [!code-vb[VSSDKSmartTagTest#11](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#11)]  
  
## <a name="implementing-the-smart-tag-tagger-provider"></a>스마트 태그 태거 공급자 구현  
  
#### <a name="to-implement-the-smart-tag-tagger-provider"></a>스마트 태그 태거 공급자를 구현하려면  
  
1.  라는 클래스를 추가 `TestSmartTagTaggerProvider` 에서 상속 되는 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>합니다. 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "text"를 <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> 의 Before = "default", 및 <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> 의 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag>합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#12](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#12)]
     [!code-vb[VSSDKSmartTagTest#12](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#12)]  
  
2.  가져오기는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> 속성으로.  
  
     [!code-csharp[VSSDKSmartTagTest#13](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#13)]
     [!code-vb[VSSDKSmartTagTest#13](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#13)]  
  
3.  <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger%2A> 메서드를 구현합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#14](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#14)]
     [!code-vb[VSSDKSmartTagTest#14](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#14)]  
  
## <a name="implementing-smart-tag-actions"></a>스마트 태그 동작 구현  
  
#### <a name="to-implement-smart-tag-actions"></a>스마트 태그 동작을 구현하려면  
  
1.  두 개의 클래스를 만듭니다. 첫 번째 클래스의 이름은 `UpperCaseSmartTagAction` 이고 두 번째 클래스의 이름은 `LowerCaseSmartTagAction`입니다. 두 클래스 모두 <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagAction>를 구현합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#15](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#15)]
     [!code-vb[VSSDKSmartTagTest#15](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#15)]  
  
     [!code-csharp[VSSDKSmartTagTest#16](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#16)]
     [!code-vb[VSSDKSmartTagTest#16](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#16)]  
  
 하나를 호출 한다는 점을 제외 하면 두 클래스는 유사 <xref:System.String.ToUpper%2A> 및 기타 호출 <xref:System.String.ToLower%2A>합니다. 다음 단계에서는 대문자 동작 클래스만 설명하지만 두 클래스를 모두 구현해야 합니다. 대문자 동작 구현 단계를 소문자 동작 구현 패턴으로 사용합니다.  
  
1.  전용 필드 집합을 선언합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#17](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#17)]
     [!code-vb[VSSDKSmartTagTest#17](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#17)]  
  
2.  필드를 설정하는 생성자를 추가합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#18](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#18)]
     [!code-vb[VSSDKSmartTagTest#18](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#18)]  
  
3.  속성을 다음과 같이 구현합니다.  
  
     [!code-csharp[VSSDKSmartTagTest#19](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#19)]
     [!code-vb[VSSDKSmartTagTest#19](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#19)]  
  
4.  구현 된 <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagAction.Invoke%2A> 범위에 있는 텍스트를 해당 대문자로 바꾸어 메서드.  
  
     [!code-csharp[VSSDKSmartTagTest#20](../snippets/csharp/VS_Snippets_VSSDK/vssdksmarttagtest/cs/testsmarttag.cs#20)]
     [!code-vb[VSSDKSmartTagTest#20](../snippets/visualbasic/VS_Snippets_VSSDK/vssdksmarttagtest/vb/testsmarttag.vb#20)]  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
 이 코드를 테스트하려면 SmartTagTest 솔루션을 빌드하고 실험적 인스턴스에서 실행합니다.  
  
#### <a name="to-build-and-test-the-smarttagtest-solution"></a>SmartTagTest 솔루션을 빌드하고 테스트하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  디버거에서 이 프로젝트를 실행하면 Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  텍스트 파일을 만들고 일부 텍스트를 입력합니다.  
  
     텍스트에서 첫 번째 단어의 첫 문자 아래에 파란색 선이 표시됩니다.  
  
4.  파란색 선 위로 포인터를 이동합니다.  
  
     포인터 근처에 단추가 표시됩니다.  
  
5.  단추를 클릭하면 두 가지 제안 동작( **대문자로 변환** 및 **소문자로 변환**)이 표시됩니다. 첫 번째 동작을 클릭하면 현재 단어의 모든 텍스트가 대문자로 변환됩니다. 두 번째 동작을 클릭하면 모든 텍스트가 소문자로 변환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 파일 이름 확장명에 콘텐츠 형식 연결](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)