---
title: JavaScript의 Windows 런타임 이벤트 처리 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7e5780a2462e8980c22c474ae6236c87aee599b
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302813"
---
# <a name="handling-windows-runtime-events-in-javascript"></a>JavaScript의 Windows 런타임 이벤트 처리
Windows 런타임 이벤트는 C++ 또는 .NET Framework에서 표현되는 방식과 다른 방식으로 JavaScript에서 표현됩니다. Windows 런타임 이벤트는 클래스 속성이 아니며 클래스의 `addEventListener` 및 `removeEventListener` 메서드에 전달되는(소문자) 문자열 식별자로 표현됩니다. 예를 들어 “positionchanged” 문자열을 `Geolocator.addEventListener` 메서드에 전달하여 [Geolocator.PositionChanged](https://msdn.microsoft.com/library/windows/apps/xaml/windows.devices.geolocation.geolocator.positionchanged.aspx) 이벤트의 이벤트 처리기를 추가할 수 있습니다.  
  
```JavaScript  
var locator = new Windows.Devices.Geolocation.Geolocator();  
locator.addEventListener(  
    "positionchanged",   
     function (ev) {  
        console.log("Got event");  
    });  
```  
  
 또한 `locator.onpositionchanged` 속성을 설정할 수도 있습니다.  
  
```JavaScript  
locator.onpositionchanged =    
    function (ev) {  
        console.log("Got event");  
    };  
```  
  
.NET/C++와 JavaScript 간의 또 다른 차이점은 이벤트 처리기에서 가져온 매개 변수의 수입니다. .NET/C++에서 처리기는 이벤트 전송자와 이벤트 데이터 두 개를 사용합니다. JavaScript에서 이 두 개는 단일 `Event` 개체로 묶입니다. 다음 예제에서 `ev` 매개 변수는 이벤트의 전송자(`target` 속성) 및 이벤트 데이터 속성(여기서는 `position`만 해당)을 둘 다 포함합니다. 이벤트 데이터 속성은 각 이벤트에 대해 문서화되는 속성입니다.
  
```JavaScript  
function (ev) {  
    console.log("Sender: " + ev.target);  
    console.log("Position: " +  
        ev.position.latitude + "," +  
        ev.position.longitude);  
};  
```  
  
> [!IMPORTANT]
>  Windows 런타임 기능은 Internet Explorer에서 실행되는 앱에는 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript에서 Windows 런타임 사용](../jswinrt/using-the-windows-runtime-in-javascript.md)
