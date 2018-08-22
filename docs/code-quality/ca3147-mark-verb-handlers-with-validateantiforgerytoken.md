---
title: '표시 동사 처리기 ValidateAntiForgeryToken CA3147:'
ms.date: 08/08/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 4b4369cfd310be9322d17b8bdbfe79880f2aa579
ms.sourcegitcommit: 96a6d1f16d06ca28d309d05b6e9fbd52f628cdbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40008705"
---
# <a name="ca3147-mark-verb-handlers-with-validateantiforgerytoken"></a>표시 동사 처리기 ValidateAntiForgeryToken CA3147:

|||
|-|-|
|TypeName|MarkVerbHandlersWithValidateAntiForgeryToken|
|CheckId|CA3147|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

ASP.NET MVC 컨트롤러 동작 메서드를 사용 하 여 표시 되지 않습니다 <xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute?displayProperty=fullName>, 또는 같은 HTTP 동사를 지정 하는 특성 <xref:Microsoft.AspNetCore.Mvc.HttpGetAttribute?displayProperty=fullName> 또는 <xref:Microsoft.AspNetCore.Mvc.AcceptVerbsAttribute?displayProperty=fullName>합니다.

## <a name="rule-description"></a>규칙 설명

ASP.NET MVC 컨트롤러를 디자인할 때 교차 사이트 요청 위조 공격 주의 해야 합니다. 교차 사이트 요청 위조 공격을 ASP.NET MVC 컨트롤러에 인증된 된 사용자를 악성 요청을 보낼 수 있습니다. 자세한 내용은 [ASP.NET MVC 및 웹 페이지에서 XSRF/CSRF 방지](/aspnet/mvc/overview/security/xsrfcsrf-prevention-in-aspnet-mvc-and-web-pages)합니다.

이 규칙에서는 ASP.NET MVC 컨트롤러 작업 메서드 중 하나:

- 가 <xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute> HTTP GET을 포함 하지 않고 허용 된 HTTP 동사를 지정 합니다.

- 허용 된 동사를로 HTTP GET을 지정 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- HTTP GET 요청을 처리 하 고 잠재적으로 해로운 부작용이 없는 ASP.NET MVC 컨트롤러 작업에 대 한 추가 <xref:Microsoft.AspNetCore.Mvc.HttpGetAttribute> 방법입니다.

   ASP.NET MVC 컨트롤러 작업이 HTTP GET을 처리 하는 요청 하 고 중요 한 데이터를 수정 하는 등 잠재적으로 해로운 의도 하지 않은 경우 응용 프로그램은 교차 사이트 요청 위조 공격에 취약 합니다.  HTTP POST, PUT 또는 DELETE 요청에만 중요 한 작업을 수행할 수 있도록 응용 프로그램을 다시 디자인 해야 합니다.

- HTTP POST를 처리 하는 ASP.NET MVC 컨트롤러 작업에 대 한 PUT 또는 DELETE 요청을 추가 <xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute> 및 허용 되는 HTTP 동사를 지정 하는 속성 (<xref:Microsoft.AspNetCore.Mvc.AcceptVerbsAttribute>, <xref:Microsoft.AspNetCore.Mvc.HttpPostAttribute>합니다 <xref:Microsoft.AspNetCore.Mvc.HttpPutAttribute>, 또는 <xref:Microsoft.AspNetCore.Mvc.HttpDeleteAttribute>). 호출 해야 하는 또한 <xref:Microsoft.AspNetCore.Mvc.ViewFeatures.HtmlHelper.AntiForgeryToken%2A?displayProperty=nameWithType> MVC 뷰 또는 Razor 웹 페이지입니다. 예를 들어 참조 [edit 메서드를 검사 하 고 뷰 편집](/aspnet/mvc/overview/getting-started/introduction/examining-the-edit-methods-and-edit-view)합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

- ASP.NET MVC 컨트롤러 작업에 해로운 파생 작업이 없습니다.

- 응용 프로그램을 다른 방식으로 위조 방지 토큰을 확인합니다.

## <a name="validateantiforgerytoken-attribute-example"></a>ValidateAntiForgeryToken 특성 예제

### <a name="violation"></a>위반

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            // You don't want an attacker to specify to who and how much money to transfer.

            return null;
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpPost]
        [ValidateAntiForgeryToken]
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            return null;
        }
    }
}
```

## <a name="httpget-attribute-example"></a>HttpGet 특성 예제

### <a name="violation"></a>위반

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult Help(int topicId)
        {
            // This Help method is an example of a read-only operation with no harmful side effects.
            return null;
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpGet]
        public ActionResult Help(int topicId)
        {
            return null;
        }
    }
}
```
