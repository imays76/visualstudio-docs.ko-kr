---
title: '연습: 사용자 지정 XML 부분에 콘텐츠 컨트롤 바인딩'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- PlainTextContentControl, binding to a custom XML part
- custom XML parts, binding to content controls
- content controls [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], content controls
- DropDownListContentControl, binding items to a custom XML part
- DatePickerContentControl, binding to a custom XML part
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5989100376dd04d1fcfa57efff11042f2e2c8454
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53899654"
---
# <a name="walkthrough-bind-content-controls-to-custom-xml-parts"></a>연습: 사용자 지정 XML 부분에 콘텐츠 컨트롤 바인딩
  이 연습에서는 문서에 저장된 XML 데이터에 Word에 대한 문서 수준 사용자 지정의 콘텐츠 컨트롤을 바인딩하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word를 사용 하면 이라는 XML 데이터를 저장할 수 있습니다 *사용자 지정 XML 부분*, 문서에 있습니다. 사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤을 바인딩하여 이 데이터의 표시를 제어할 수 있습니다. 이 연습의 예제 문서에서는 사용자 지정 XML 부분에 저장된 직원 정보를 표시합니다. 문서를 열면 콘텐츠 컨트롤에 XML 요소의 값이 표시됩니다. 콘텐츠 컨트롤의 텍스트에 대한 모든 변경 내용은 사용자 지정 XML 부분에 저장됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
- 디자인 타임에 문서 수준 프로젝트의 Word 문서에 콘텐츠 컨트롤 추가  
  
- 콘텐츠 컨트롤에 바인딩할 요소를 정의하는 XML 데이터 파일 및 XML 스키마 만들기  
  
- 디자인 타임에 문서에 XML 스키마 연결  
  
- 런타임에 문서의 사용자 지정 XML 부분에 XML 파일의 콘텐츠를 추가합니다.  
  
- 사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤 바인딩  
  
- XML 스키마에 정의된 값 집합에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> 바인딩  
  
  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="create-a-new-word-document-project"></a>새 Word 문서 프로젝트 만들기  
 연습에서 사용할 Word 문서를 만듭니다.  
  
### <a name="to-create-a-new-word-document-project"></a>새 Word 문서 프로젝트를 만들려면  
  
1.  이름을 사용 하 여 Word 문서 프로젝트를 만듭니다 **EmployeeControls**합니다. 솔루션에 대한 새 문서를 만듭니다. 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에서 새 Word 문서가 열리고 추가 합니다 **EmployeeControls** 프로젝트가 **솔루션 탐색기**합니다.  
  
## <a name="add-content-controls-to-the-document"></a>문서에 콘텐츠 컨트롤 추가  
 사용자가 직원에 대한 정보를 보거나 편집할 수 있는 세 가지 형식의 콘텐츠 컨트롤을 포함하는 테이블을 만듭니다.  
  
### <a name="to-add-content-controls-to-the-document"></a>문서에 콘텐츠 컨트롤을 추가하려면  
  
1. 에 호스트 된 Word 문서에는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너 리본에서 선택 합니다 **삽입** 탭 합니다.  
  
2. 에 **테이블** 그룹에서 **테이블**, 2 열, 3 개의 행이 있는 테이블을 삽입 합니다.  
  
3. 다음 열과 비슷하도록 첫 번째 열에 텍스트를 입력합니다.  
  
   ||  
   |-|  
   |**직원 이름**|  
   |**채용 날짜**|  
   |**제목**|  
  
4. 테이블의 두 번째 열, 첫 번째 행을 선택 합니다 (옆 **Employee Name**).  
  
5. 리본에서 선택 합니다 **개발자** 탭 합니다.  
  
   > [!NOTE]  
   >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다. 자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)합니다.  
  
6. 에 **컨트롤** 그룹을 선택 합니다 **텍스트** 단추 ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") 를추가할<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>첫째 셀으로 합니다.  
  
7. 테이블의 두 번째 열, 두 번째 행을 선택 합니다 (옆 **Hire Date**).  
  
8. **컨트롤** 그룹을 선택 합니다 **날짜 선택** 단추 ![DatePickerContentControl](../vsto/media/datepicker.gif "DatePickerContentControl") 를추가하려면<xref:Microsoft.Office.Tools.Word.DatePickerContentControl> 두 번째 셀에 있습니다.  
  
9. 테이블의 두 번째 열, 세 번째 행을 선택 합니다 (옆 **Title**).  
  
10. 에 **컨트롤** 그룹에서 선택 합니다 **드롭 다운 목록** 단추 ![DropDownListContentControl](../vsto/media/dropdownlist.gif "DropDownListContentControl") 추가할 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> 마지막 셀입니다.  
  
    이 프로젝트에 대한 전체 사용자 인터페이스입니다. 지금 프로젝트를 실행하는 경우 첫 번째 행에 텍스트를 입력하고 두 번째 행에서 날짜를 선택할 수 있습니다. 다음 단계는 XML 파일의 문서에 표시하려는 데이터를 연결하는 것입니다.  
  
## <a name="create-the-xml-data-file"></a>XML 데이터 파일 만들기  
 일반적으로 파일 또는 데이터베이스와 같은 외부 소스에서 사용자 지정 XML 부분에 저장할 XML 데이터를 가져옵니다. 이 연습에서는 문서의 콘텐츠 컨트롤에 바인딩할 요소로 표시된, 직원 데이터를 포함하는 XML 파일을 만듭니다. 런타임에 데이터를 사용할 수 있게 하려면 사용자 지정 어셈블리에 XML 파일을 리소스로 포함합니다.  
  
#### <a name="to-create-the-data-file"></a>데이터 파일을 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  에 **템플릿을** 창 **XML 파일**합니다.  
  
3.  파일 이름을 **employees.xml**를 선택 합니다 **추가** 단추입니다.  
  
     합니다 **employees.xml** 파일이 코드 편집기에서 열립니다.  
  
4.  내용을 대체 합니다 **employees.xml** 다음 텍스트를 사용 하 여 파일입니다.  
  
    ```xml 
    <?xml version="1.0" encoding="utf-8" ?>  
    <employees xmlns="http://schemas.microsoft.com/vsto/samples">  
      <employee>  
        <name>Karina Leal</name>  
        <hireDate>1999-04-01</hireDate>  
        <title>Manager</title>  
      </employee>  
    </employees>  
    ```  
  
5.  **솔루션 탐색기**를 선택 합니다 **employees.xml** 파일입니다.  
  
6.  에 **속성** 창에서 합니다 **빌드 작업** 속성 값을 변경한 후 **포함 리소스**합니다.  
  
     이 단계에서는 프로젝트를 빌드할 때 XML 파일을 어셈블리에 리소스로 포함합니다. 이렇게 하면 런타임에 XML 파일의 내용에 액세스할 수 있습니다.  
  
## <a name="create-an-xml-schema"></a>XML 스키마 만들기  
 사용자 지정 XML 부분의 단일 요소에 콘텐츠 컨트롤을 바인딩하려는 경우 XML 스키마를 사용할 필요가 없습니다. 그러나 값 집합에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 바인딩하려면 앞에서 만든 XML 데이터 파일의 유효성을 검사하는 XML 스키마를 만들어야 합니다. XML 스키마는 `title` 요소에 대한 가능한 값을 정의합니다. 이 연습의 뒷부분에서 이 요소에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 바인딩합니다.  
  
#### <a name="to-create-an-xml-schema"></a>XML 스키마를 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  에 **템플릿을** 창 **XML 스키마**합니다.  
  
3.  스키마의 이름을 **employees.xsd** 선택 합니다 **추가** 단추입니다.  
  
     스키마 디자이너가 열립니다.  
  
4.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 **employees.xsd**를 선택한 후 **코드 보기**합니다.  
  
5.  내용을 대체 합니다 **employees.xsd** 다음 스키마 파일입니다.  
  
    ```xml
    <?xml version="1.0" encoding="utf-8" ?>  
    <xs:schema xmlns="http://schemas.microsoft.com/vsto/samples"   
        targetNamespace="http://schemas.microsoft.com/vsto/samples"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema"  
        elementFormDefault="qualified">  
      <xs:element name="employees" type="EmployeesType"></xs:element>  
      <xs:complexType name="EmployeesType">  
        <xs:all>  
          <xs:element name="employee" type="EmployeeType"/>  
        </xs:all>  
      </xs:complexType>  
      <xs:complexType name="EmployeeType">  
        <xs:sequence>  
          <xs:element name="name" type="xs:string" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="hireDate" type="xs:date" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="title" type="TitleType" minOccurs="1" maxOccurs="1"/>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:simpleType name="TitleType">  
        <xs:restriction base="xs:string">  
          <xs:enumeration value ="Engineer"/>  
          <xs:enumeration value ="Designer"/>  
          <xs:enumeration value ="Manager"/>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:schema>  
    ```  
  
6.  에 **파일** 메뉴에서 클릭 **모두 저장** 에 변경 내용을 저장 하는 **employees.xml** 및 **employees.xsd** 파일입니다.  
  
## <a name="attach-the-xml-schema-to-the-document"></a>XML 스키마 문서에 연결  
 `title` 요소의 유효한 값에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 바인딩하려면 문서에 XML 스키마를 연결해야 합니다.  
  
### <a name="to-attach-the-xml-schema-to-the-document--includeword15shortvstoincludesword-15-short-mdmd"></a>XML 스키마 문서를 연결 하려면 ( [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)])  
  
1.  활성화 **EmployeeControls.docx** 디자이너에서 합니다.  
  
2.  리본에서 선택 합니다 **개발자** 탭을 선택한 다음는 **Add-ins** 단추.  
  
3.  에 **템플릿 및 추가 기능** 대화 상자를 선택 합니다 **XML 스키마** 탭을 선택한 다음를 **스키마 추가** 단추.  
  
4.  이동할를 **employees.xsd** 스키마 앞에서 만든 프로젝트 디렉터리에 있으며 다음을 선택 합니다 **열려** 단추.  
  
5.  선택 된 **확인** 단추를 **스키마 설정** 대화 상자.  
  
6.  선택 된 **확인** 를 닫으려면 단추를 합니다 **템플릿 및 추가 기능** 대화 상자.  
  
### <a name="to-attach-the-xml-schema-to-the-document-word-2010"></a>문서에 XML 스키마를 연결하려면(Word 2010)  
  
1.  활성화 **EmployeeControls.docx** 디자이너에서 합니다.  
  
2.  리본에서 선택 합니다 **개발자** 탭 합니다.  
  
3.  에 **XML** 그룹에서 선택 합니다 **스키마** 단추입니다.  
  
4.  에 **템플릿 및 추가 기능** 대화 상자를 선택 합니다 **XML 스키마** 탭을 선택한 다음를 **스키마 추가** 단추.  
  
5.  로 이동 합니다 **employees.xsd** 선택한 프로젝트 디렉터리에는 앞에서 만든 스키마를 **열려** 단추.  
  
6.  선택 된 **확인** 단추를 **스키마 설정** 대화 상자.  
  
7.  선택 된 **확인** 를 닫으려면 단추를 합니다 **템플릿 및 추가 기능** 대화 상자.  
  
     합니다 **XML 구조** 작업창이 열립니다.  
  
8.  닫기 합니다 **XML 구조** 작업창입니다.  
  
## <a name="add-a-custom-xml-part-to-the-document"></a>문서에 사용자 지정 XML 부분 추가  
 XML 파일의 요소에 콘텐츠 컨트롤을 바인딩하려면 먼저 문서의 새 사용자 지정 XML 부분에 XML 파일의 내용을 추가해야 합니다.  
  
### <a name="to-add-a-custom-xml-part-to-the-document"></a>문서에 사용자 지정 XML 부분을 추가하려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 **ThisDocument.cs** 또는 **ThisDocument.vb**를 선택한 후 **코드 보기**합니다.  
  
2.  `ThisDocument` 클래스에 다음 선언을 추가합니다. 이 코드는 문서에 사용자 지정 XML 부분을 추가하는 데 사용할 여러 개체를 선언합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#1](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#1)]  
  
3.  다음 메서드를 `ThisDocument` 클래스에 추가합니다. 이 메서드는 어셈블리에 리소스로 포함된 XML 데이터 파일의 내용을 가져오고 XML 문자열로 반환합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#3)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#3](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#3)]  
  
4.  다음 메서드를 `ThisDocument` 클래스에 추가합니다. `AddCustomXmlPart` 메서드는 메서드에 전달된 XML 문자열을 포함하는 새 사용자 지정 XML 부분을 만듭니다.  
  
     사용자 지정 XML 부분이 한 번만 생성되도록 이 메서드는 일치하는 GUID를 가진 사용자 지정 XML 부분이 문서에 없는 경우에만 사용자 지정 XML 부분을 만듭니다. 이 메서드를 처음 호출하면 <xref:Microsoft.Office.Core._CustomXMLPart.Id%2A> 속성의 값이 `employeeXMLPartID` 문자열에 저장됩니다. `employeeXMLPartID` 문자열의 값은 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성을 사용하여 선언되었으므로 문서에 유지됩니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#4)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#4](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#4)]  
  
## <a name="bind-the-content-controls-to-elements-in-the-custom-xml-part"></a>사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤을 바인딩하십시오.  
 각 콘텐츠 컨트롤을 사용 하 여 사용자 지정 XML 부분에 있는 요소에 바인딩하는 **XMLMapping** 각 콘텐츠 컨트롤의 속성입니다.  
  
### <a name="to-bind-the-content-controls-to-elements-in-the-custom-xml-part"></a>사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤을 바인딩하려면  
  
1.  다음 메서드를 `ThisDocument` 클래스에 추가합니다. 이 메서드는 사용자 지정 XML 부분의 요소에 각 콘텐츠 컨트롤을 바인딩하고 <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>의 날짜 표시 형식을 설정합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#5)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#5](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#5)]  
  
## <a name="run-your-code-when-the-document-is-opened"></a>문서가 열릴 때 코드를 실행 합니다.  
 문서를 열 때 사용자 지정 XML 부분을 만들고 사용자 지정 컨트롤을 데이터에 바인딩합니다.  
  
### <a name="to-run-your-code-when-the-document-is-opened"></a>문서를 열 때 코드를 실행하려면  
  
1.  `ThisDocument` 클래스의 `ThisDocument_Startup` 메서드에 다음 코드를 추가합니다. 이 코드에서 XML 문자열을 가져옵니다 합니다 **employees.xml** 파일인 문서에서 새 사용자 지정 XML 부분에 XML 문자열을 추가 하 고 사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤을 바인딩합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/CSharp/EmployeeControls/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#2](../vsto/codesnippet/VisualBasic/EmployeeControls/ThisDocument.vb#2)]  
  
## <a name="test-the-project"></a>프로젝트 테스트  
 문서를 열면 콘텐츠 컨트롤이 사용자 지정 XML 부분에 있는 요소의 데이터를 표시합니다. 클릭할 수는 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> 에 대 한 세 가지 유효한 값 중 하나를 선택 합니다 `title` 에 정의 된 요소를 **employees.xsd** 파일. 콘텐츠 컨트롤의 데이터를 편집하는 경우 문서의 사용자 지정 XML 부분에 새 값이 저장됩니다.  
  
### <a name="to-test-the-content-controls"></a>콘텐츠 컨트롤을 테스트하려면  
  
1.  키를 눌러 **F5** 프로젝트를 실행 합니다.  
  
2.  문서의 테이블이 다음 테이블과 유사한지 확인합니다. 두 번째 열의 각 문자열은 문서의 사용자 지정 XML 부분에 있는 요소에서 가져옵니다.  
  
    |||  
    |-|-|  
    |**직원 이름**|**Karina Leal**|  
    |**채용 날짜**|**1999 년 4 월 1 일**|  
    |**제목**|**관리자**|  
  
3.  오른쪽에 있는 셀을 선택 합니다 **Employee Name** 셀 및 다른 이름을 입력 합니다.  
  
4.  오른쪽에 있는 셀을 선택 합니다 **Hire Date** 셀 및 날짜 선택 컨트롤에서 다른 날짜를 선택 합니다.  
  
5.  오른쪽에 있는 셀을 선택 합니다 **제목** 셀 및 드롭다운 목록에서 새 항목을 선택 합니다.  
  
6.  문서를 저장한 후 닫습니다.  
  
7.  파일 탐색기에서 엽니다는 *\bin\Debug* 프로젝트 위치 아래에 있는 폴더입니다.  
  
8.  바로 가기 메뉴를 열고 **EmployeeControls.docx** 를 선택한 후 **이름 바꾸기**합니다.  
  
9. 파일 이름을 **EmployeeControls.docx.zip**합니다.  
  
     합니다 **EmployeeControls.docx** 문서가 Open XML 형식으로 저장 됩니다. 이 문서의 바꾸어 합니다 *.zip* 파일 이름 확장명을 문서의 내용을 검사할 수 있습니다. Open XML에 대 한 자세한 내용은 기술 문서를 참조 하세요 [소개 Office (2007) Open XML 파일 형식](/previous-versions/office/developer/office-2007/aa338205(v=office.12))합니다.  
  
10. 엽니다는 **EmployeeControls.docx.zip** 파일입니다.  
  
11. 엽니다는 **customXml** 폴더입니다.  
  
12. 바로 가기 메뉴를 열고 **item2.xml** 를 선택한 후 **오픈**합니다.  
  
     이 파일에는 문서에 추가한 사용자 지정 XML 부분이 포함됩니다.  
  
13. `name`, `hireDate` 및 `title` 요소에 문서의 콘텐츠 컨트롤에 입력한 새 값이 포함되어 있는지 확인합니다.  
  
14. 닫기 합니다 **item2.xml** 파일입니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음 항목에서 콘텐츠 컨트롤을 사용하는 방법에 대해 자세히 알아볼 수 있습니다.  
  
-   사용 가능한 모든 콘텐츠 컨트롤을 사용하여 서식 파일을 만듭니다. 자세한 내용은 [연습: 콘텐츠 컨트롤을 사용 하 여 템플릿을 만드는](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)합니다.  
  
-   문서가 닫혀 있는 동안 사용자 지정 XML 부분의 데이터를 수정합니다. 다음에 사용자가 문서를 열면 XML 요소에 바인딩된 콘텐츠 컨트롤이 새 데이터를 표시합니다.  
  
-   콘텐츠 컨트롤을 사용하여 문서 부분을 보호합니다. 자세한 내용은 [방법: 콘텐츠 컨트롤을 사용 하 여 문서 부분 보호](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [확장 된 개체를 사용 하 여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [콘텐츠 컨트롤](../vsto/content-controls.md)   
 [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [방법: 콘텐츠 컨트롤을 사용 하 여 문서 부분 보호](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍 방식으로 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)  
