---
title: 호출 트리 뷰 - .NET 메모리 샘플링 데이터 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Tree view
ms.assetid: fbb6cb60-420b-4ca9-8306-2494f7d321fe
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c24cec082e7935275d776832d96a63e910c7997a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47565321"
---
# <a name="call-tree-view---net-memory-sampling-data"></a>호출 트리 뷰 - .NET 메모리 샘플링 데이터
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [호출 트리 뷰-.NET 메모리 샘플링 데이터](https://docs.microsoft.com/visualstudio/profiling/call-tree-view-dotnet-memory-sampling-data)입니다.  
  
호출 트리 뷰에는 프로파일링 된 응용 프로그램에서 이동한 함수 실행 경로가 표시됩니다. 트리의 루트는 응용 프로그램 또는 구성 요소에 대한 진입점입니다. 각 함수 노드에는 호출한 모든 함수 및 이러한 함수 호출에 대한 .NET 메모리 할당 데이터가 나열됩니다.  
  
 호출 트리 뷰의 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스에 대한 값입니다. 비율 값은 프로파일링 실행 시 총 할당 수 또는 크기와 함수 인스턴스 값을 비교하여 계산됩니다.  
  
## <a name="highlighting-the-execution-hot-path"></a>실행 부하 과다 경로 강조 표시  
 호출 트리 뷰에서는 가장 크거나 대부분의 메모리 개체를 만든 프로세스 또는 함수의 실행 경로를 확장하고 강조 표시할 수 있습니다. 최대 활성 경로를 표시하려면 프로세스 또는 함수를 마우스 오른쪽 단추로 클릭한 후 **실행 부하 과다 경로 확장**을 클릭합니다.  
  
## <a name="setting-the-call-tree-root-node"></a>호출 트리 루트 노드 설정  
 프로파일링 실행 시 각 프로세스는 루트 노드로 표시됩니다. 호출 트리 뷰의 시작 노드를 다른 노드로 설정하려면 시작 노드로 설정하려는 노드를 마우스 오른쪽 단추로 클릭하고 **루트 설정**을 선택합니다.  
  
 루트 노드를 설정하면 선택한 노드의 하위 트리를 제외한 다른 모든 항목이 뷰에서 제거됩니다. 호출 트리 뷰 창에서 마우스 오른쪽 단추로 클릭하고 **루트 다시 설정**을 선택하여 루트 노드를 보고 있던 노드로 다시 설정할 수 있습니다.  
  
|열|설명|  
|------------|-----------------|  
|**프로세스 ID**|프로파일링 실행의 PID(프로세스 ID)입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수가 포함된 모듈의 경로입니다.|  
|**소스 파일**|이 함수의 정의가 포함된 소스 파일입니다.|  
|**함수 이름**|함수의 정규화된 이름입니다.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**함수 주소**|함수의 주소입니다.|  
|**수준**|호출 트리에서 함수의 깊이입니다.|  
|**포함 할당**|호출 트리의 부모 함수가 호출한 이 함수의 인스턴스에 의해 할당된 개체의 수입니다. 이 수는 자식 함수에서 만든 할당을 포함합니다.|  
|**포함 할당 비율(%)**|이 함수의 포함 할당으로, 프로파일링 실행 시 생성된 모든 개체의 비율입니다.|  
|**제외 할당**|호출 트리의 부모 함수가 호출한 이 함수의 인스턴스에 의해 할당된 개체의 수입니다. 이 수는 자식 함수에서 만든 할당을 포함하지 않습니다.|  
|**제외 할당 비율(%)**|호출 트리의 부모 함수가 호출한 함수 인스턴스의 제외 할당이었던 프로파일링 실행 시 만든 모든 개체의 비율입니다.|  
|**포함 바이트**|호출 트리의 부모 함수가 호출한 이 함수의 인스턴스에 의해 할당된 메모리의 바이트 수입니다. 이 수는 자식 함수에서 만든 할당을 포함합니다.|  
|**포함 바이트 비율(%)**|이 함수의 포함 할당으로, 프로파일링 실행 시 할당된 모든 메모리 바이트의 비율입니다.|  
|**제외 바이트**|호출 트리의 부모 함수가 호출한 이 함수의 인스턴스에 의해 할당된 메모리의 바이트 수입니다. 이 수는 자식 함수에서 만든 할당을 포함하지 않습니다.|  
|**제외 바이트(%)**|이 함수의 제외 할당으로, 프로파일링 실행 시 할당된 모든 메모리 바이트의 비율입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [호출 트리 뷰 - 계측](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [호출 트리 뷰](../profiling/call-tree-view-sampling-data.md)   
 [호출 트리 뷰](../profiling/call-tree-view-instrumentation-data.md)


