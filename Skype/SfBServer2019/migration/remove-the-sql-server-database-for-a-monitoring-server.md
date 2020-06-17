---
title: 모니터링 서버용 SQL Server 데이터베이스 제거
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
description: 모니터링 서버를 제거한 후에는 서버 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753330"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>모니터링 서버용 SQL Server 데이터베이스 제거

모니터링 서버를 제거한 후에는 서버 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.
    
2. 토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **SQL server 저장소**로 이동한 다음, 제거 되거나 다시 구성 된 모니터링 서버에 연결 된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    
3. 토폴로지를 게시한 후 복제 상태를 확인합니다.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server에서 데이터베이스 파일을 제거하려면

1. SQL Server 기반 서버에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL Server 서버에 대해 SQL Server sysadmins 그룹의 구성원 이어야 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
3. 명령줄에 다음을 입력합니다.
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    여기서 _\<FQDN\>_ 은 데이터베이스 서버의 FQDN (정규화 된 도메인 이름) 이며, _\<instance\>_ 선택적 명명 된 데이터베이스 인스턴스입니다. 
    
4. **제거-CsDataBase** cmdlet에서 작업을 확인 하 라는 메시지가 표시 되 면 정보를 읽고, 계속 하려면 Y (또는 Enter) 키를 누르고, 오류가 있으면 enter 키를 눌러 cmdlet을 중지 합니다. 
    

