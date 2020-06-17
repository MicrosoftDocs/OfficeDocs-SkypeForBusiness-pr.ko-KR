---
title: 프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거
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
description: 프런트 엔드 풀을 제거 하거나 다른 데이터베이스를 사용 하도록 풀을 다시 구성한 후에는 해당 풀 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753410"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거

프런트 엔드 풀을 제거 하거나 다른 데이터베이스를 사용 하도록 풀을 다시 구성한 후에는 해당 풀 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 열고 기존 토폴로지를 다운로드 합니다. 
    
2. 토폴로지 작성기에서 **공유 구성 요소** 를 탐색 한 다음 **sql server 저장소**로 이동한 후 제거 되거나 다시 구성 된 프런트 엔드 풀과 연결 된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    
3. 토폴로지를 게시 한 후 복제 상태를 확인 합니다. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>SQL server에서 사용자 및 응용 프로그램 데이터베이스를 제거 하려면

1. SQL server에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL server에 대해 SQL Server sysadmins 그룹의 구성원 이어야 합니다. 
    
2. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
3. 풀 사용자 저장소에 대 한 데이터베이스를 제거 하려면 다음을 입력 합니다.
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    여기서 _\<FQDN\>_ 은 데이터베이스 서버의 FQDN (정규화 된 도메인 이름) 이며, _\<instance\>_ 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다. 
    
4. 풀 응용 프로그램 저장소에 대 한 데이터베이스를 제거 하려면 다음을 입력 합니다.
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    여기서 _\<FQDN\>_ 은 데이터베이스 서버의 FQDN 이며 _\<instance\>_ 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다. 
    
5. **제거-CsDataBase** cmdlet에서 작업을 확인 하 라는 메시지가 표시 되 면 정보를 읽고, 계속 하려면 Y (또는 Enter) 키를 누르고, 오류가 있으면 enter 키를 눌러 cmdlet을 중지 합니다. 
    

