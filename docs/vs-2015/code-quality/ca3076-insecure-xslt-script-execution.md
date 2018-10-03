---
title: 'CA3076: 안전 하지 않은 XSLT 스크립트 실행 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53cb7a46-c564-488f-bc51-0e210a7853c9
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d814c71e7ce1cbde850357feab9251ee58fd1358
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47592355"
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: 안전하지 않은 XSLT 스크립트 실행
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA3076: 안전 하지 않은 XSLT 스크립트 실행](https://docs.microsoft.com/visualstudio/code-quality/ca3076-insecure-xslt-script-execution)합니다.

|||
|-|-|
|TypeName|InsecureXSLTScriptExecution|
|CheckId|CA3076|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 .NET 응용 프로그램에서 비보안 방식으로 [XSLT(Extensible Stylesheets Language Transformations)](https://support.microsoft.com/en-us/kb/313997) 를 실행하는 경우 프로세서는 공격자에게 중요한 정보를 노출하여 서비스 거부 및 사이트 간 공격을 유발할 수 있는 [신뢰할 수 없는 URI 참조를 확인](http://msdn.microsoft.com/en-us/ba3e4d4f-1ee7-4226-a51a-78a1f1b5bd8a) 할 수 있습니다.

## <a name="rule-description"></a>규칙 설명
 [XSLT](http://msdn.microsoft.com/en-us/6377ce5f-3c45-42a6-b7a9-ec8da588b60c) 는 XML 데이터를 변환하기 위한 W3C(World Wide Web 콘소시엄) 표준입니다. XSLT는 XML 데이터를 HTML, 고정 길이 텍스트, 쉼표로 구분된 텍스트 또는 기타 XML 형식 등으로 변환하기 위한 스타일시트를 작성하는 데 일반적으로 사용됩니다. 이 기능은 프로젝트에서 기본적으로는 금지되어 있지만 사용하도록 설정할 수 있습니다.

 공격 노출 영역을 노출 하지 하도록이 규칙 때마다 트리거는 XslCompiledTransform.<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 안전 하지 않은 조합 인스턴스의 받습니다 <xref:System.Xml.Xsl.XsltSettings> 및 <xref:System.Xml.XmlResolver>, 악성 스크립트를 처리를 허용 하는 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

-   안전 하지 않은 XsltSettings 인수를 XsltSettings 바꿉니다.<xref:System.Xml.Xsl.XsltSettings.Default%2A> 또는 인스턴스를 사용 하 여 문서 함수 및 스크립트 실행 비활성화입니다.

-   <xref:System.Xml.XmlResolver> 인수를 null 또는 <xref:System.Xml.XmlSecureResolver> 인스턴스로 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 입력 출처를 신뢰할 수 있는지 확신할 수 없으면 이 경고의 규칙이 표시되지 않도록 설정하지 않도록 합니다.

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation"></a>위반

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
         void TestMethod()
        {
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
             var settings = XsltSettings.TrustedXslt;
             var resolver = new XmlUrlResolver();
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
        }
    }
} 
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        void TestMethod()
        {
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
            var settings = XsltSettings.Default;
            var resolver = new XmlUrlResolver();
            xslCompiledTransform.Load("testStylesheet", settings, resolver);
        }
    }
}
```

### <a name="violation"></a>위반

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
            }
            catch { throw; }
            finally { }
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                settings.EnableDocumentFunction = false;
                settings.EnableScript = false;
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver);
            }
            catch { throw; }
            finally { }
        }
    }
}
```


