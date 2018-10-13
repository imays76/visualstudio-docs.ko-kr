---
title: 데이터 저장 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataRow.RowState
- DataSet.GetChanges
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- DBDirect methods
- updating data
- data [Visual Studio], saving
- TableAdapter DBDirect methods
- databases, updating
- TableAdapter.Update method
- data [Visual Studio], updating
- saving data
- updating databases
ms.assetid: 21d2b115-62e4-4ac9-a873-dcbb535b8af8
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: dc671d60ff37e9853dc64a62cbc1b91a6914e0e3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49249303"
---
# <a name="saving-data"></a>데이터 저장
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

데이터를 저장 하는 프로세스를 유지 원래 데이터 저장소에서 SQL Server와 같은 일반적으로 관계형 데이터베이스를 다시 응용 프로그램의 데이터 모델의 데이터를 변경입니다.  
  
 데이터 모델을 사용 하 여 데이터 소스 업데이트는 일반적으로 이루어집니다. 새 정보를 사용 하 여 데이터 모델을 업데이트 하는 첫 번째 단계-새 레코드를 레코드를 변경 하거나 레코드를 삭제 합니다. 두 번째 단계는 변경 내용을 다시 데이터베이스에 데이터 모델에 저장 하는 것입니다.  
  
 개념 및 작업 데이터 저장과 관련 된 다음 항목에 설명 합니다.  
  
## <a name="related-topics"></a>관련 항목  
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)  
 데이터 집합을 데이터베이스에 변경 내용을 저장 하기 위해 변경 내용에 대 한 정보를 추적 하는 방법 및 데이터 집합의 변경 내용을 적용 하는 방법을 간략하게를 설명 합니다.  
  
 [엔터티 데이터 저장](../data-tools/saving-entity-data.md)  
 변경 내용을 저장 하는 방법에 설명 [ADO.NET Entity Framework](http://msdn.microsoft.com/library/a437041f-6899-4ae7-96ce-aabf528d7205) 하 고 [WCF Data Services 4.5](http://msdn.microsoft.com/library/73d2bec3-7c92-4110-b905-11bb0462357a) 응용 프로그램입니다.