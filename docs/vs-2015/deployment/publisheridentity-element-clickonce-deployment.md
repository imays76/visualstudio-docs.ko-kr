---
title: '&lt;publisherIdentity&gt; 요소 (ClickOnce 배포) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 4c11e8ed9a3e0b4341708fc849462fbc476dc395
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553347"
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt; 요소 (ClickOnce 배포)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [ &lt;publisherIdentity&gt; 요소 (ClickOnce 배포)](https://docs.microsoft.com/visualstudio/deployment/publisheridentity-element-clickonce-deployment)합니다.  
  
이 배포 매니페스트에 서명한 게시자에 대한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `publisherIdentity` 요소는 서명 된 매니페스트에 필요 합니다. 다음 표에서 특성을 보여 줍니다는 `publisherIdentity` 요소를 지원 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수. 이 응용 프로그램을 게시 하는 파티의 id를 설명 합니다.|  
|`issuerKeyHash`|필수. 인증서 발급자의 공개 키의 sha-1 해시를 포함합니다.|  
  
#### <a name="parameters"></a>매개 변수  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
  
## <a name="subhead"></a>부제목



