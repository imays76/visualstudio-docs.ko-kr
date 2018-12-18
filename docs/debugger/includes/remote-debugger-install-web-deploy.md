---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: c22ba73b464f91bf3036541304cdf94e8660970d
ms.sourcegitcommit: 1c675dae7c348defb32d9f7ccf7079a1062a1c4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48244115"
---
1. Visual Studio에서 웹 배포에서 응용 프로그램을 배포 하려는 경우 서버에서 최신 버전의 웹 배포를 설치 합니다.

    웹 배포를 설치 하려면 사용 합니다 [웹 플랫폼 설치 관리자 (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)합니다. (선택 IIS에서 웹 플랫폼 설치 관리자 링크를 찾으려면 **IIS** 서버 관리자의 왼쪽된 창에서. 서버를 마우스 오른쪽 단추로 누르고 **인터넷 정보 서비스 (IIS) 관리자**.)

    웹 플랫폼 설치 관리자에서 찾을 있습니다 웹 배포 응용 프로그램 탭에서. 설치 관리자에서 직접 가져올 수도 있습니다는 [Microsoft 다운로드 센터](https://www.microsoft.com/search/result.aspx?q=webdeploy&form=dlc)합니다. 

2. 열어 웹 배포 제대로 실행 되는지 확인 **제어판 > 시스템 및 보안 > 관리 도구 > 서비스** 했는지 **웹 배포 에이전트 서비스가** 중인지 ( 서비스 이름은 이전 버전에서 다른)입니다.

    에이전트 서비스를 실행 하지 않는 경우 시작 합니다. 없는 전혀,로 이동 **제어판 > 프로그램 > 프로그램 제거**를 찾을 **Microsoft Web Deploy <version>** 합니다. 하기로 **변경** 설치를 선택 하 고 **로컬 하드 드라이브에 설치 됩니다** 웹 배포 구성 요소에 대 한 합니다. 변경 설치 단계를 완료 합니다.