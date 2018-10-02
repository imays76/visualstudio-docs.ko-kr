---
title: 데이터 사용자 인터페이스 요소 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.data.tablemappings
- vs.datasource.choosebindingsourcedialog
- vs.datasource.choosedatasourceinstancedlg
- vs.data.editrelation
- DSD_EditMultiKey
- vs.datasource.RealtionBuilder
- vs.xmldesigner.editkey
- vs.xmldesigner.choosekey
- vs.data.generatedataset
- vs.data.configurationerror
- vs.data.DSD_MissingConnections_Message
- vs.datasource.choosedesigndatasourcedlg
- vs.data.datapreview
- vs.data.editforeignkeyconstraint
- vs.datasource.choosedataconectordialog
- vs.data.dataadapterpreview
- vs.data.configurationwizard
- vs.data.datapreviewdialog
- DSD_EditMultiKeyHelpID
- vs.data.advancedoptions
- vs.data.previewscript
- vs.data.datasourcelogin
- vs.syncdesigner.syncnowconflictiondialog
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- dialog boxes, data
- data [Visual Studio], dialog boxes
ms.assetid: 90943baf-5bd1-4eef-927f-f82485979fde
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: b699d44b8aa5b8c9e1e917e4e361414ff1a9afd4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541460"
---
# <a name="data-user-interface-elements"></a>데이터 사용자 인터페이스 요소
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 섹션에서는 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 또는 Visual C# 응용 프로그램에서 데이터 액세스를 디자인할 때 사용하는 모든 대화 상자와 마법사에 대한 정보를 제공합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="in-this-section"></a>섹션 내용  
 [데이터 스마트 태그](http://msdn.microsoft.com/en-us/1e0a848f-c57b-47ab-b884-eaaa40726f43)  
 데이터에 사용할 수 있는 몇 가지 스마트 태그 명령에 대한 정보를 제공합니다.  
  
 [추가 데이터 집합 대화 상자](http://msdn.microsoft.com/en-us/0e03c0ff-212b-4bfa-ac51-3c2adb71ead0)  
 기존 형식화 된 데이터 집합 또는 형식화 되지 않은 새 데이터 집합 (의 인스턴스를 **System.Data.Dataset** 클래스)를 폼 이나 구성 요소입니다.  
  
 [고급 SQL 생성 옵션 대화 상자](http://msdn.microsoft.com/en-us/41420450-1ff4-4a1a-b85b-6f6901538fef)  
 업데이트, 낙관적 동시성 및 데이터 집합 새로 고침 옵션을 지정하여 데이터 어댑터에 대해 SQL 문 또는 저장 프로시저가 작성되는 방식을 제어할 수 있습니다.  
  
 [데이터 원본 인스턴스 대화 상자를 선택 합니다.](http://msdn.microsoft.com/en-us/51c47f06-fdc5-453e-9178-0a5a2c5c9f34)  
 프로젝트의 데이터 집합 목록에서 원하는 데이터 집합을 선택할 수 있습니다.  
  
 [대화 상자를 사용 하 여 병합 하는 데이터 원본 선택](http://msdn.microsoft.com/en-us/accafff7-f6bd-481c-a121-fe8a76cd681d)  
 여러 데이터 소스를 사용할 수 있는 경우 병합할 데이터 소스를 선택할 수 있습니다.  
  
 [선택 키 대화 상자](http://msdn.microsoft.com/en-us/4ddbfbb7-a80a-412a-b80d-291d86376ca3)  
 열에 다중 키 제약 조건이 적용되는 경우 키를 선택할 수 있습니다.  
  
 [컬렉션 편집기](http://msdn.microsoft.com/library/030095bd-fb9a-4b21-b628-fc1cc5985bb7)  
 컬렉션의 개별 멤버를 만들고 편집할 수 있는 여러 컬렉션 편집기 관련 항목에 대한 링크를 제공합니다.  
  
 [연결이 없습니다.](http://msdn.microsoft.com/en-us/bb9b2e12-7f76-4ee5-acbb-5d20116ee044)  
 응용 프로그램 설정에 없는 연결 문자열에 대한 참조가 데이터 집합에 포함되어 있으면 알림을 제공합니다.  
  
 [데이터 어댑터 구성 오류 대화 상자](http://msdn.microsoft.com/en-us/9ce65cd2-0c7d-4f51-8685-d68be5f3009b)  
 Visual Studio에서 데이터 어댑터 인스턴스 만들기를 시도하고 이 속성을 설정하는 동안 발생한 하나 이상의 오류가 표시됩니다.  
  
 [데이터 어댑터 구성 마법사](http://msdn.microsoft.com/en-us/efff90cb-0e4c-4eb3-87dc-65dd9d418809)  
 데이터 어댑터가 데이터베이스에서 데이터를 데이터 집합으로 읽어들인 다음 다시 쓰는 데 사용되는 SQL 명령 또는 저장 프로시저를 구성합니다. 이 항목에서는 마법사를 실행하는 방법과 마법사가 완료된 후 수행할 작업에 대해 설명합니다.  
  
 [데이터 어댑터 미리 보기 대화 상자](http://msdn.microsoft.com/en-us/1f614cd3-4530-457e-84af-00ccbaea08cc)  
 데이터 어댑터가 데이터 집합에 데이터를 채우는 방법을 확인할 수 있습니다. 따라서 어댑터가 예상한 데이터를 반환하며 테이블 매핑이 정상적으로 작동하는지 여부와 각 매개 변수 값의 영향을 테스트하는 데 유용합니다.  
  
 [데이터 소스 로그인 대화 상자](http://msdn.microsoft.com/en-us/6f2d9a57-53c3-4841-bd37-a3643eb68d2e)  
 아직 인증되지 않은 데이터 소스(대개 데이터베이스)에 대한 액세스를 요청할 수 있습니다.  
  
 [도구 상자, 데이터 집합 탭](http://msdn.microsoft.com/en-us/fa5f2d6f-924d-4262-ba1b-e9e7f90e7764)  
 형식화된 데이터 집합에 추가할 수 있는 개체가 표시됩니다.  
  
 [연결 문자열 대화 상자에 암호를 포함 하 시겠습니까](http://msdn.microsoft.com/en-us/193696a7-5213-4396-8328-05ac2df6ee94)  
 연결 문자열에 암호가 포함되는지 여부를 제어할 수 있습니다.  
  
 [키 편집 대화 상자](http://msdn.microsoft.com/en-us/f5c80e39-3a42-4284-b222-6ca009fd9675)  
 키를 정의하고 편집할 수 있습니다.  
  
 [외래 키 제약 조건 대화 상자](http://msdn.microsoft.com/en-us/45d15629-1f4d-40a7-8708-c9ddfebedc1e)  
 다른 테이블에 관련된 데이터 집합 테이블의 열 하나 이상에 대해 외래 키 제약 조건을 적용할 수 있습니다.  
  
 [데이터 집합 대화 상자를 생성 합니다.](http://msdn.microsoft.com/en-us/c0efdbaf-13b1-4ee8-ade6-f8a784126cdc)  
 하나 이상의 데이터 어댑터가 제공하는 정보에서 새 형식화된 데이터 집합을 생성하고 기존 데이터 집합에 테이블을 추가할 수 있습니다.  
  
 [여러 개의 Bindingsource 대화 상자](http://msdn.microsoft.com/en-us/db76f70c-4fb5-479d-9b64-a67158d48f97)  
 둘 이상의 <xref:System.Windows.Forms.BindingSource>를 사용할 수 있는 경우 사용할 <xref:System.Windows.Forms.BindingSource>를 선택할 수 있습니다.  
  
 [데이터 미리 보기 대화 상자](http://msdn.microsoft.com/en-us/aa4f0d04-2695-4bb8-946d-54a97ae7287f)  
 프로젝트에서 쿼리가 반환하는 데이터를 검토할 수 있습니다.  
  
 [미리 보기 SQL 스크립트 대화 상자](http://msdn.microsoft.com/en-us/e9571e8b-821c-492d-9bc8-b44eba898bdd)  
 일부분으로 표시 합니다 [데이터 어댑터 구성 마법사](http://msdn.microsoft.com/en-us/efff90cb-0e4c-4eb3-87dc-65dd9d418809) 마법사 데이터 읽기 및 쓰기 저장된 프로시저를 만드는 데 사용할 SQL 스크립트를 확인할 수 있도록 합니다.  
  
 [관계 대화 상자](http://msdn.microsoft.com/en-us/ab8f4b0e-af4c-4725-a550-e2b2ebe43a02)  
 관계를 만들 수 있습니다 (한 **DataRelation** 개체) 데이터 집합의 두 데이터 테이블에 부모-자식 레코드에 대 한 정보를 유지 관리 하는 합니다.  
  
 [검색 조건 작성기 대화 상자](http://msdn.microsoft.com/library/0b306b92-f35e-45ef-a4be-3f653cd00c3d)  
 데이터 바인딩된 Windows Form에 대해 매개 변수가 있는 쿼리를 만들고 해당 쿼리를 실행하는 데 필요한 컨트롤을 자동으로 추가할 수 있습니다.  
  
 [테이블 매핑 대화 상자](http://msdn.microsoft.com/en-us/fb4cec1e-f3c8-4773-b409-c2de15293fea)  
 데이터 집합 테이블의 열과 동일한 데이터베이스 테이블 또는 기타 데이터 소스의 열을 지정할 수 있습니다.  
  
 [Unique 제약 조건 대화 상자](http://msdn.microsoft.com/en-us/e71a60d7-fae2-4bd0-a1e8-43aae351707d)  
 형식화되지 않은 데이터 집합의 테이블에 포함된 하나 이상의 열에 대해 UNIQUE 제약 조건을 적용할 수 있습니다.  
  
## <a name="related-sections"></a>관련 단원  
 [데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)  
 Visual Basic 및 Visual C# 응용 프로그램에서 데이터에 액세스하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [응용 프로그램에 데이터를 가져오는 중](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [데이터 저장](../data-tools/saving-data.md)