---
title: '방법: Northwind 데이터베이스에 연결 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- connections [Visual Studio], Northwind database
- Northwind sample database
ms.assetid: cc6cb79f-d035-41f8-b398-8d4a45922bfb
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 3f64fa378029546f7a3126b324c282f6a91d7231
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49897636"
---
# <a name="how-to-connect-to-the-northwind-database"></a>방법: Northwind 데이터베이스에 연결
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio를 사용하여 데이터베이스 응용 프로그램을 만드는 방법을 배우려면 Northwind 데이터베이스에 연결하여 해당 제품의 설명서에 나와 있는 여러 예제를 연습해 보아야 합니다. 진행하는 예제에 따라 SQL Server 또는 데이터베이스 파일의 데이터베이스(예: Microsoft Access 또는 SQL Server용 데이터베이스)에 연결됩니다.  
  
## <a name="creating-data-connections-to-the-northwind-database"></a>Northwind 데이터베이스에 대한 데이터 연결 만들기  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-a-data-connection-to-the-northwind-database-sql-server"></a>Northwind 데이터베이스에 대한 데이터 연결을 만들려면(SQL Server)  
  
1. 에 **뷰** 메뉴 선택 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
2. **서버 탐색기**/**데이터베이스 탐색기**, 바로 가기 메뉴를 열고 **데이터 연결** 선택 하 고 **연결 추가**.  
  
    선택한 후 **연결 추가**하거나, 합니다 **데이터 소스 선택** 대화 상자 또는 **연결 추가** 대화 상자가 표시 됩니다.  
  
3. 경우는 **데이터 원본 선택** 대화 상자가 나타나면 **Microsoft SQL Server**를 선택한 후 **확인**합니다.  
  
    경우는 **연결 추가** 대화 상자가 표시 됩니다 및 **데이터 원본** 아닙니다 **Microsoft SQL Server (SqlClient)** 를 선택 합니다 **변경** 버튼을 클릭 하는 **변경 데이터 원본** 대화 상자에서 **Microsoft SQL Server**를 선택한 후는 **확인** 단추.  
  
4. 에 **서버 이름** 목록에서 Northwind 데이터베이스가 있는 서버의 이름을 지정 합니다.  
  
5. 선택 하거나 SQL Server 및 Northwind 데이터베이스 버전의 요구 사항에 따라 **Windows 인증 사용** 선택 하거나 **SQL Server 인증 사용** 사용자 이름을 입력 하 고 SQL Server를 실행 하는 컴퓨터에 로그온 할 암호입니다.  
  
6. Northwind 데이터베이스를 선택 합니다 **데이터베이스 이름 선택 또는 입력** 목록입니다.  
  
7. 선택할 **연결 테스트** Northwind 데이터베이스에 대 한 연결을 확인 합니다.  
  
8. **확인**을 선택합니다.  
  
    Northwind 데이터베이스에 데이터 연결에 추가 됩니다 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
   SQL Server 데이터베이스의 원격 인스턴스에 연결할 수 있을 뿐 아니라 데이터베이스가 포함된 실제 파일에 직접 연결할 수도 있습니다. 그러므로 응용 프로그램의 일부분으로 데이터베이스 파일을 배포할 수 있는 프로젝트에 데이터베이스 파일을 추가할 수 있습니다. 다음 로컬 데이터베이스 파일은 현재 지원: SQL Server Compact 데이터베이스 파일 (.sdf), [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] SQL Server Express 데이터베이스 파일 (.mdf) 및 Microsoft Access 데이터베이스 파일 (.mdb 또는.accdb).  
  
#### <a name="to-create-a-data-connection-to-the-northwind-databasesql-server-database-file-mdf"></a>Northwind 데이터베이스(SQL Server 데이터베이스 파일(.mdf)에 대한 데이터 연결을 만들려면  
  
1.  에 **뷰** 메뉴 선택 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
2.  **서버 탐색기**/**데이터베이스 탐색기**, 바로 가기 메뉴를 열고 **데이터 연결** 선택 하 고 **연결 추가**.  
  
     선택한 후 **연결 추가**하거나, 합니다 **연결 추가** 대화 상자 또는 **데이터 소스 선택** 대화 상자가 표시 됩니다.  
  
3.  경우는 **데이터 원본 선택** 선택 대화 상자가 나타나면 **Microsoft SQL Server 데이터베이스 파일**를 선택한 후는 **확인**.  
  
4.  경우는 **연결 추가** 확인 대화 상자가 나타나면 합니다 **데이터 원본** 로 설정 되어 **Microsoft SQL Server 데이터베이스 파일 (SqlClient)** 합니다. 로 설정 되지 않은 경우 **Microsoft SQL Server 데이터베이스 파일 (SqlClient)**, 선택 **변경** 열려는 합니다 **데이터 소스 변경** 대화 상자에서 **Microsoft SQL Server 데이터베이스 파일**를 선택한 후 합니다 **확인** 단추입니다.  
  
5.  선택할 **찾아보기** Northwind 데이터베이스를 포함 하 여.mdf 파일을 찾습니다.  
  
6.  선택 하거나 Northwind 데이터베이스 버전의 요구 사항에 따라 **Windows 인증 사용** 선택 하거나 **SQL Server 인증** 사용자 이름 및 로그온 하는 암호를 입력 합니다 SQL Server를 실행 하는 컴퓨터입니다.  
  
7.  **확인** 단추를 선택합니다.  
  
     Northwind 데이터베이스에 데이터 연결에 추가 됩니다 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
> [!NOTE]
>  [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]에는 Northwind 데이터베이스 파일(.mdf)에 적용되는 변경 내용이 포함되어 있습니다. 정보를 참조 하세요 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)합니다.  
  
#### <a name="to-create-a-data-connection-to-the-northwind-databaseaccess-database-file-mdb-or-accdb"></a>Northwind 데이터베이스에 대한 데이터 연결을 만들려면(Access 데이터베이스 파일(.mdb 또는 .accdb))  
  
1.  에 **뷰** 메뉴 선택 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
2.  **서버 탐색기**/**데이터베이스 탐색기**, 바로 가기 메뉴를 열고 **데이터 연결** 선택 하 고 **연결 추가**.  
  
     선택한 후 **연결 추가**하거나, 합니다 **연결 추가** 대화 상자 또는 **데이터 소스 선택** 대화 상자가 표시 됩니다.  
  
3.  경우는 **데이터 원본 선택** 대화 상자가 나타나면 **Microsoft Access 데이터베이스 파일**를 선택한 후 **확인**합니다.  
  
4.  경우는 **연결 추가** 확인 대화 상자가 나타나면 합니다 **데이터 원본** 로 설정 되어 **Microsoft Access 데이터베이스 파일**합니다. 로 설정 되지 않은 경우 **Microsoft Access 데이터베이스 파일**, 선택 **변경** 열려는 합니다 **데이터 소스 변경** 대화 상자에서 **Microsoft Access 데이터베이스 파일**를 선택한 후 합니다 **확인** 단추입니다.  
  
5.  선택할 **찾아보기** Northwind 데이터베이스가 포함 된.mdb 또는.accdb 파일을 찾습니다.  
  
6.  사용 중인 Northwind 데이터베이스 버전에 필요한 경우 사용자 이름과 암호를 입력합니다.  
  
7.  **확인**을 선택합니다.  
  
     Northwind 데이터베이스에 데이터 연결에 추가 됩니다 **서버 탐색기**/**데이터베이스 탐색기**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)   
 [Microsoft Access 2010을 사용한 데이터 프로그래밍](http://msdn.microsoft.com/library/office/ff965871.aspx)   
 [데이터 연습](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)