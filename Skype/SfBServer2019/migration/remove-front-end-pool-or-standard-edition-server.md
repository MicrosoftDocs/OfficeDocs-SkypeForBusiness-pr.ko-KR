---
title: 프런트 엔드 풀 또는 Standard Edition 서버 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 항목에서는 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 제거 하는 프로세스를 안내 합니다. 프런트 엔드 풀을 제거 하면 풀에 속한 각 프런트 엔드 서버를 그룹 제거 프로세스의 일부로 제거 합니다. Standard Edition 프런트 엔드 서버를 제거 하는 경우 토폴로지 작성기에서 SQL 저장소 정의를 제거 해야 합니다.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752280"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>프런트 엔드 풀 또는 Standard Edition 서버 제거

이 문서에서는 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 제거 하는 프로세스를 안내 합니다. 프런트 엔드 풀을 제거 하면 풀에 속한 각 프런트 엔드 서버를 그룹 제거 프로세스의 일부로 제거 합니다. Standard Edition 프런트 엔드 서버를 제거 하는 경우 토폴로지 작성기에서 SQL 저장소 정의를 제거 해야 합니다.
  
## <a name="to-remove-a-front-end-server-pool"></a>프런트 엔드 서버 풀을 제거하려면

1. 토폴로지 작성기를 엽니다.
    
2. 레거시 노드로 이동 합니다.
    
3. **Enterprise Edition 프런트 엔드 풀**을 확장 하 고 프런트 엔드 풀을 확장 한 후 제거 하려는 프런트 엔드 풀을 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    
4. 토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 레거시 배포 마법사를 실행 합니다. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Standard Edition 프런트 엔드 서버를 제거하려면

1. 토폴로지 작성기를 엽니다.
    
2. 레거시 설치 노드로 이동 합니다.
    
3. **Standard Edition 프런트 엔드 서버**를 확장 하 고 제거할 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    
4. **Sql 저장소**를 확장 하 고 Standard Edition 프런트 엔드 서버에 연결 된 SQL Server 데이터베이스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    
    > [!IMPORTANT]
    > Standard Edition 프런트 엔드 서버에서 배치 된 SQL Server 데이터베이스의 정의를 제거 해야 합니다. 
  
5. 토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 배포 마법사를 실행 합니다. 
    

