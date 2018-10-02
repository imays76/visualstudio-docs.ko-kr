---
title: '방법: 프로젝트의 로컬 데이터 파일 관리 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.data.LocalConnectionConverter
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- mdf files
- local data
- .mdb files
- .mdf files
- data [Visual Studio], local
- mdb files
ms.assetid: 3ffa1aa9-17e4-422c-a02f-09224828cdfc
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: b63a90a354935300c705c0bf96ae307e0468b4f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47553039"
---
# <a name="how-to-manage-local-data-files-in-your-project"></a>방법: 프로젝트의 로컬 데이터 파일 관리
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

로컬 데이터베이스 파일을 프로젝트에 파일로 포함할 수 있습니다. 로컬 데이터베이스 파일을 연결할 처음으로 프로젝트의 복사본을 만들거나 현재 위치에서 기존 파일에 연결할 선택할 수 있습니다. 기존 파일에 연결할 경우 원래 위치에 그대로 수 있습니다. 프로젝트 파일을 복사 하려는 경우 Visual Studio의 복사본을 만듭니다, 그리고 프로젝트에 추가 및 복사를 가리키도록 연결 수정 서버 탐색기에서 같은 다른 연결도 수정 됩니다.  
  
 속성의 기본 설정을 사용 하는 데이터베이스 파일의 유형에 따라 달라 집니다. 동작을 **출력 디렉터리로 복사** 속성이 웹 또는 c + + 프로젝트에 적용 되지 않습니다.  
  
 개발 하는 동안 이러한 변경 내용을 영구적으로 만들지 않고 데이터베이스에서 코드의 효과 볼 수는 것이 좋습니다. 설정에 따라 이렇게를 **출력 디렉터리로 복사** true 파일의 속성입니다. 프로젝트 빌드 또는 F5 키 될 때마다 파일이 bin 폴더에 복사 됩니다 하 고 프로젝트의 루트 폴더에 파일로 하지 해당 파일에 변경 내용이 있습니다. 루트 프로젝트 폴더에 데이터베이스 파일을 사용 하 여 데이터베이스 스키마 나 데이터를 편집 하는 경우에 변경 **서버 탐색기**하십시오 **데이터베이스 탐색기** 또는 다른 도구 창.  
  
 다음 테이블의 설정을 설명 합니다 **출력 디렉터리로 복사** 속성입니다.  
  
|설정|동작|  
|-------------|--------------|  
|**변경 된 내용만 복사** (.sdf 파일에 대 한 기본값)|데이터베이스 파일을 프로젝트 디렉터리에서 복사 됩니다는 **bin** 디렉터리 첫 번째 시간 프로젝트가 빌드됩니다. 프로젝트를 빌드하면 프로젝트가 빌드될 때마다 합니다 **수정한 날짜** 파일의 속성이 비교 됩니다. 프로젝트 폴더에서 파일이 최신 파일인 경우 복사 합니다 **bin** 폴더, 현재 그곳에 있는 파일을 대체 합니다. 경우에 파일을 **bin** 폴더 최신 이면 파일이 복사 됩니다. 이 설정은 유지 런타임 중 데이터 변경 될 때마다 응용 프로그램을 실행 하는 데이터 변경 내용을 저장 내용이 표시 되는지 다음에 응용 프로그램을 실행 합니다. **주의:** .mdb 또는.mdf 파일에 대해이 옵션을 권장 하지 않습니다. 데이터베이스 파일에는 데이터에 변경 되지 않습니다 하는 경우에 변경할 수 있습니다. 데이터 파일에 대 한 연결을 열기만 해도 (예를 들어,를 확장 하 여는 **테이블** 노드에서 **서버 탐색기**) 최신으로 표시할 수 있습니다.|  
|**항상 복사** (.mdf 및.mdb 파일에 대 한 기본값)|데이터베이스 파일을 응용 프로그램을 빌드할 때마다 프로젝트 디렉터리에서 /bin 디렉터리로 복사 됩니다. 따라서 응용 프로그램을 작성 하 고 변경 내용을 /bin 디렉터리에 파일에 저장 하는 경우 해당 변경 내용은 원본 파일 /bin 디렉터리에 복사 되는 다음에 덮어씁니다.|  
|**복사 안 함**|파일 복사 되거나 프로젝트 시스템을 덮어써 되지 않습니다. 수동으로 복사 해야 파일을 프로젝트 디렉터리에서 출력 디렉터리에이 설정을 사용 하는 경우.|  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-respond-to-the-local-database-file-dialog-box"></a>로컬 데이터베이스 파일 대화 상자에 응답  
  
-   클릭 **예** Visual Studio 프로젝트에 데이터베이스 파일을 복사 하 고 프로젝트의 복사본을 가리키도록 연결을 수정 하기를 원하는 경우. 프로젝트의 데이터베이스 파일을 사용 하 여 작업에 대 한 자세한 내용은 참조 하세요. [로컬 데이터 개요](../data-tools/local-data-overview.md)합니다.  
  
-   클릭 **No** 프로젝트에 데이터베이스 파일을 복사 하려면 Visual Studio를 원하지 않는 경우. 대신 원래 위치에 파일 및 데이터베이스 파일에 연결 지점 추가 되지 않습니다 파일로 프로젝트에.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 데이터에에서 연결 하는 로컬 데이터베이스 파일 (Windows Forms)](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)   
 [Access 데이터베이스의 데이터에 연결(Windows Forms)](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)