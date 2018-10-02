---
title: '샘플 XSD 파일: 단순한 스키마 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7e1dde1-b4f6-4371-add4-935b68ec77d7
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d070712fc96c086092d3f16176dfc370dc5d9987
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550872"
---
# <a name="sample-xsd-file-simple-schema"></a>샘플 XSD 파일: 단순한 스키마
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [샘플 XSD 파일: 단순한 스키마](https://docs.microsoft.com/visualstudio/xml-tools/sample-xsd-file-simple-schema)합니다.  
  
  
다음 XSD 파일은 XSD 스키마 디자이너 설명서의 다양한 예제에서 사용됩니다. 이 파일은 단순한 구매 주문 스키마입니다.  
  
```xml  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:tns="http://tempuri.org/PurchaseOrderSchema.xsd"   
           targetNamespace="http://tempuri.org/PurchaseOrderSchema.xsd"   
           elementFormDefault="qualified">  
 <xsd:element name="PurchaseOrder" type="tns:PurchaseOrderType"/>  
 <xsd:complexType name="PurchaseOrderType">  
  <xsd:sequence>  
   <xsd:element name="ShipTo" type="tns:USAddress" maxOccurs="2"/>  
   <xsd:element name="BillTo" type="tns:USAddress"/>  
  </xsd:sequence>  
  <xsd:attribute name="OrderDate" type="xsd:date"/>  
 </xsd:complexType>  
  
 <xsd:complexType name="USAddress">  
  <xsd:sequence>  
   <xsd:element name="name"   type="xsd:string"/>  
   <xsd:element name="street" type="xsd:string"/>  
   <xsd:element name="city"   type="xsd:string"/>  
   <xsd:element name="state"  type="xsd:string"/>  
   <xsd:element name="zip"    type="xsd:integer"/>  
  </xsd:sequence>  
  <xsd:attribute name="country" type="xsd:NMTOKEN" fixed="US"/>  
 </xsd:complexType>  
</xsd:schema>  
```



