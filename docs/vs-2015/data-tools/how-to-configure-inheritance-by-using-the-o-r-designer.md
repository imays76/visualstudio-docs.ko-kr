---
title: '방법: O-r 디자이너를 사용 하 여 상속 구성 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e594af12-e777-434a-bc08-7dd2dac84cdc
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ccfbd40fd9fd62921ff6f0661f87dca2995ae8fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554353"
---
# <a name="how-to-configure-inheritance-by-using-the-or-designer"></a>방법: O/R 디자이너를 사용 하 여 상속 구성
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: O-r 디자이너를 사용 하 여 상속 구성](https://docs.microsoft.com/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)합니다.  
  
  
[!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)]([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)])는 관계형 시스템에서 주로 구현되는 단일 테이블 상속 개념을 지원합니다. 단일 테이블 상속에서는 부모 정보와 자식 정보에 대한 필드를 모두 포함하는 데이터베이스 테이블이 하나 있습니다. 관계형 데이터의 경우 판별자 열에는 해당 레코드가 어느 클래스에 속해 있는지를 판별하는 값이 포함됩니다.  
  
 예를 들어 회사에 고용되어 있는 모든 사람들이 포함되어 있는 Persons 테이블을 생각해 봅시다. 어떤 사람들은 사원이고 어떤 사람들은 관리자입니다. Persons 테이블에는 관리자의 경우 1 값이 들어 있고 사원의 경우 2 값이 들어 있는 `EmployeeType`이라는 열이 있으며 이 열이 판별자 열입니다. 이 시나리오에서는 직원 서브클래스를 만든 후 `EmployeeType` 값이 2인 레코드로만 클래스를 채울 수 있습니다. 각 클래스에서 적용되지 않는 열은 제거할 수도 있습니다.  
  
 상속을 사용하고 관계형 데이터에 대응하는 개체 모델을 만드는 것은 조금 복잡할 수 있습니다. 다음 절차에서는 O/R 디자이너를 사용하여 상속을 구성하는 데 필요한 단계를 요약한 것입니다. 기존 테이블과 열을 참조하지 않고 일반 단계를 따르는 것이 어려울 수 있으므로 데이터를 사용하는 연습이 제공되었습니다. 상속을 사용 하 여 구성에 대 한 자세한 단계별 지침에 대 한는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]를 참조 하세요 [연습: 만들기 LINQ to SQL 클래스를 사용 하 여 단일 테이블 상속 (O/R 디자이너)에 의해](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md).  
  
### <a name="to-create-inherited-data-classes"></a>상속된 데이터 클래스를 만들려면  
  
1.  엽니다는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 추가 하 여는 **LINQ to SQL 클래스** 기존 Visual Basic 또는 C# 프로젝트에 항목입니다.  
  
2.  기본 클래스로 사용할 테이블을 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]로 끌어 옵니다.  
  
3.  두 번째 테이블 복사본을 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]로 끌어 와서 이름을 바꿉니다. 이것을 파생 클래스 또는 서브클래스라고 합니다.  
  
4.  클릭 **상속** 에 **Object Relational Designer** 탭을 **도구 상자**, 서브 클래스 (이름을 바꾼 테이블)를 클릭 한 다음 및 기본 클래스에 연결 합니다.  
  
    > [!NOTE]
    >  클릭 합니다 **상속** 항목에 **도구 상자** 및 마우스 단추를 놓으면, 3 단계에서 생성 된 클래스의 두 번째 복사를 클릭 한 다음 2 단계에서 만든 첫 번째 클래스를 클릭 합니다. 상속 선의 화살표가 첫 번째 클래스를 가리킵니다.  
  
5.  각 클래스에서 연결에 사용되지 않으므로 표시하지 않을 개체 속성을 모두 삭제합니다. 연결에 사용 되는 개체 속성을 삭제 하려고 하면 오류가 발생 합니다. [속성을 \<속성 이름 > 연결에 참여 하 고 있으므로 삭제할 수 없습니다 \<연결 이름 >](../data-tools/the-property-property-name-cannot-be-deleted-because-it-is-participating-in-the-association-association-name.md).  
  
    > [!NOTE]
    >  파생 클래스는 기본 클래스에 정의된 속성을 상속하므로 각 클래스에 동일한 열은 정의할 수 없습니다. 열은 속성으로 구현됩니다. 기본 클래스의 속성에서 상속 한정자를 설정함으로써 파생 클래스에서 열을 만들 수 있습니다. 자세한 내용은 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/en-us/2167e8f5-1225-4b13-9ebd-02591ba90213)합니다.  
  
6.  [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]에서 상속 선을 선택합니다.  
  
7.  에 **속성** 창에서 **Discriminator Property** 수업에서 레코드를 구분 하는 데 사용 되는 열 이름으로 합니다.  
  
8.  설정 된 **Derived Class Discriminator Value** 속성을 상속 된 형식으로 레코드를 지정 하는 데이터베이스의 값입니다. 이는 판별자 열에 저장된 값이며 상속된 클래스를 지정하는 데 사용되는 값입니다.  
  
9. 설정 된 **기본 클래스 판별자 값** 속성을 기본 형식으로 레코드를 지정 하는 값입니다. 이는 판별자 열에 저장된 값이며 기본 클래스를 지정하는 데 사용되는 값입니다.  
  
10. 선택적으로 설정할 수도 있습니다는 **Inheritance Default** 속성 정의 된 상속 코드와 일치 하지 않는 행을 로드할 때 사용 되는 상속 계층 구조의 형식을 지정 합니다. 즉, 레코드의 판별자 열의 값이 일치 하지 않는의 값을 **Derived Class Discriminator Value** 하거나 **Base Class Discriminator Value** 속성, 레코드 로 지정 된 형식으로 로드 합니다 **Inheritance Default**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [PAVE Visual Studio 2012의 데이터 응용 프로그램 개발의 새로운 기능](http://msdn.microsoft.com/en-us/3d50d68f-5f44-4915-842f-6d42fce793f1)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [연습: 단일 테이블 상속 (O/R 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
 [빌드에 없음: Visual Basic의 상속](http://msdn.microsoft.com/en-us/e5e6e240-ed31-4657-820c-079b7c79313c)   
 [상속](http://msdn.microsoft.com/library/81d64ee4-50f9-4d6c-a8dc-257c348d2eea)

