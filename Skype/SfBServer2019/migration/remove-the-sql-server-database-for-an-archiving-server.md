---
title: 보관 서버용 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 보관 서버를 제거한 후에는 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 토폴로지 작성기에서 정의를 제거 하려면 다음 절차를 사용 하 여 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
ms.openlocfilehash: ab76c8ebc629206827be0a4c0a5477eff54a0923
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241816"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>보관 서버용 SQL Server 데이터베이스 제거

보관 서버를 제거한 후에는 풀 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 토폴로지 작성기에서 정의를 제거 하려면 다음 절차를 사용 하 여 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.
    
2. 토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **sql server 저장소**로 이동한 다음 제거 되거나 다시 구성 된 보관 서버와 연결 된 sql server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    
3. 토폴로지를 게시 한 다음 복제 상태를 확인 합니다. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server에서 데이터베이스 파일을 제거 하려면

1. SQL Server에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL Server에 대 한 SQL Server sysadmins 그룹의 구성원 이어야 합니다. 
    
2. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
3. 명령줄에 다음을 입력 합니다.
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    여기서 _ \<fqdn\> _ 은 데이터베이스 서버의 fqdn (정규화 된 도메인 이름)이 고 _ \<인스턴스\> _ 는 명명 된 데이터베이스 인스턴스 (즉, 정의 된 경우)입니다. 
    
4. **제거-CsDataBase** cmdlet에서 작업을 확인 하 라는 메시지가 표시 되 면 정보를 읽은 다음 Y (또는 enter) 키를 눌러 계속 진행 하거나 N 키를 누른 다음 cmdlet을 중지 하려는 경우 (오류가 있는 경우)를 입력 합니다. 
    

