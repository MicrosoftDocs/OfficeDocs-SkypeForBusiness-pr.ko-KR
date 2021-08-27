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
ms.localizationpriority: medium
description: 이 항목에서는 프런트 엔드 풀 또는 프런트 엔드 서버를 제거하는 프로세스를 Standard Edition 안내합니다. 프런트 엔드 풀을 제거하면 풀 제거 프로세스의 일부로 풀에 속하는 각 프런트 엔드 서버를 제거합니다. 프런트 엔드 Standard Edition 제거할 때 토폴로지 작성기에서 SQL Store 정의를 제거해야 합니다.
ms.openlocfilehash: 04ff2120fcbbe0c914a0a105669083eeb13a8347
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589252"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>프런트 엔드 풀 또는 Standard Edition 서버 제거

이 문서에서는 프런트 엔드 풀 또는 프런트 엔드 서버를 제거하는 프로세스를 Standard Edition 안내합니다. 프런트 엔드 풀을 제거하면 풀 제거 프로세스의 일부로 풀에 속하는 각 프런트 엔드 서버를 제거합니다. 프런트 엔드 Standard Edition 제거할 때 토폴로지 작성기에서 SQL Store 정의를 제거해야 합니다.
  
## <a name="to-remove-a-front-end-server-pool"></a>프런트 엔드 서버 풀을 제거하려면

1. 토폴로지 작성기를 엽니다.
    
2. 레거시 노드로 이동합니다.
    
3. 프런트 **엔드 Enterprise Edition** 확장하고, 프런트 엔드 풀을 확장하고, 제거할 프런트 엔드 풀을 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**
    
4. 토폴로지 게시, 복제 상태 확인, 필요한 경우 레거시 배포 마법사를 실행합니다. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Standard Edition 프런트 엔드 서버를 제거하려면

1. 토폴로지 작성기를 엽니다.
    
2. 레거시 설치 노드로 이동합니다.
    
3. 프런트 **Standard Edition** 서버를 확장하고 제거할 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**
    
4. SQL 저장소를 확장하고 SQL Server 프런트 엔드 서버와 연결된 Standard Edition 데이터베이스를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**
    
    > [!IMPORTANT]
    > 프런트 엔드 서버에서 함께 SQL Server 데이터베이스의 정의를 Standard Edition 합니다. 
  
5. 토폴로지 게시, 복제 상태 확인, 필요한 경우 배포 마법사를 실행합니다. 
    

